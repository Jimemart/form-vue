<template>
  <div class="container">
    <form>
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <my-full-name @fullNameDone="userData.name = $event"></my-full-name>
          <div class="form-group">
            <label for="email">Email</label>
            <input type="text" name="email" class='form-control' v-model="userData.email">
          </div>
          <div class="form-group">
            <label for="password">Password</label>
            <input type="password" name="password" class='form-control' v-model="userData.password">
          </div>

        </div>
      </div>
      <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
                    <h4>Store Data?</h4>
                    <label for="yes">
                        <input
                                type="radio"
                                id="yes"
                                value="Yes"
                                v-model="storeMe"> Yes
                    </label>
                    <label for="no">
                        <input
                                type="radio"
                                id="no"
                                value="No"
                                v-model="storeMe"> No
                    </label>
                </div>
      </div>
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
          <button class="btn btn-primary" @click.prevent="submited = true">Submit!</button>
        </div>
      </div>
    </form>
    <hr>
    <div class="row" v-if="submited">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-default">
          <div class="cpanel-heading">
            <h4>Your Data</h4>
          </div>
          <div class="panel-body">
            <p>Full name: {{userData.name}}</p>
            <p>Mail: {{userData.email}}</p>
            <p>Password: {{userData.password}}</p>
            <p>Store in Database?: {{storeMe}} </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import FullName from './FullName.vue'

export default {
  components:{
    'my-full-name': FullName
  },
  data: ()=>{
   return {
     userData : {
      name : '',
      password : '',
      email: ''
      },
      storeMe: '',
      submited : false
    }
  },
  methods:{
    showme(val){
      console.log(val)
    }
  }
}
</script>

<style>

</style>
