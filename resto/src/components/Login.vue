<script>
    import axios from "axios";
    export default{
        name:"LoginPage",
        data(){
            return{
                email:"",
                password:"",
            }
        },
        methods:{
            async login(){
                let result = await axios.get(`http://localhost:3000/users?email=${this.email}&password=${this.password}`)
                console.warn(result)
                if(result.status == 201){
                    localStorage.setItem("user-info",JSON.stringify(result.data[0]))
                    this.$router.push({name:"Home"})
                }
            }
        }
    }
</script>
<template>
    <img src="../assets/logo.png" alt="" class="logo">
    <h1>Sign Up</h1>
    <div class="register">
        <input type="email" v-model="email" placeholder="Enter email"/>
        <input type="password" v-model="password" placeholder="Enter password">
        <button v-on:click="login" >Log In</button>
    </div>
    <p>
        Need to register? <router-link to="/sign-up" class="link">Register</router-link>
    </p>
</template>
<style scoped>
    .logo{
        width: 200px;
    }
    .register input{
        width: 300px;
        height: 40px;
        padding-left: 20px;
        display: block;
        margin-bottom: 30px;
        margin-right: auto;
        margin-left: auto;
        border: 1px solid rrgb(150, 36, 36)ed;
        border-radius: 10px;
    }
    .register button{
        width: 320px;
        height: 40px;
        padding-left: 20px;
        display: block;
        margin-bottom: 30px;
        margin-right: auto;
        margin-left: auto;
        background: rgb(150, 36, 36);
        color: white;
        cursor: pointer; 
        border: none;
        font-size: large;
        border-radius: 10px;
    }
    .register button:hover{
        background: rgb(150, 36, 36);
    }
    .link{
        text-decoration: none;
        color: rgb(150, 36, 36);
        border: 1px solid rgb(150, 36, 36);
        padding: 3px;
        border-radius: 5px;
    }
    .link:hover{
        background: rgb(150, 36, 36);
        color:white;
        
    }
</style>