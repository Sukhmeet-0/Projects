<template>
    <Header/>
    <h1>Welcome {{ name }} on home page</h1>
</template>
<script>
    import Header from './Header.vue'
    export default{
        name:"UpdatePage",
        data(){
            return{
                name:''
            }
        },
        components:{
            Header
        },
        mounted(){
            let user = localStorage.getItem('user-info')
            if(!user){
                this.$router.push({name:"SignUp"})
            }
        }
    }
</script>
<style>

</style>