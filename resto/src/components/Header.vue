<script>
    export default{
        name:"HeaderPage",
        methods:{
            logout(){
                console.log("logout");
                localStorage.clear();
                this.$router.push({name:"LoginPage"})
            }
        }
    }
</script>
<template>
    <div class="nav">
        <a href="">Home</a>
        <a href="">Add Restaurant</a>
        <a href="">Update Restaurant</a>
        <a v-on:click="logout" href="">Logout</a>
    </div>
</template>
<style scoped>
    .nav{
        background-color: rgb(150, 36, 36);
        overflow: hidden;
    }
    .nav a{
        float: left;
        color: #f2f2f2f2;
        padding: 14px 16px;
        text-align: center;
        font-size: 17px;
        text-decoration: none;
        margin-left: 5px;
    }
    .nav a:hover{
        background: rgb(122, 27, 27);
        color: white;
    }
</style>