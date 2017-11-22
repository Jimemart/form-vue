<template>
<div>
<div class="form-group">
     <label for="name">First Name</label>
     <input type="text" name="name" class='form-control' @input="createFull($event.target.value, true)" :value="userData.name">
</div>
<div class="form-group">
     <label for="last">Last Name</label>
     <input type="text" name="last" class='form-control' @input="createFull($event.target.value, false)" :value="userData.last">
</div>
</div>

</template>

<script>
export default {
    data (){
        return {
            userData:{
                name: '',
                last: ''
            },
            fullName: ''
            
        }
    },
    methods:{
        sayHi(){
           console.log('hola')

        },
        createFull(val, boo){
            if(boo){
                this.userData.name = val
                this.fullName = val + ' ' + this.userData.last
                console.log(this.userData)
                this.sendInfo()
            }else{
                this.userData.last = val
                
                this.fullName = this.userData.name + ' ' + val
                this.sendInfo()
            }
        },
        sendInfo(){
            
            this.$emit('fullNameDone', this.fullName)
        }
    },
    
};
</script>

<style>

</style>
