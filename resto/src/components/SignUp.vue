<script>
    import axios from 'axios'
    export default{
        name:"SignUp",
        data(){
            return{
                name:"",
                email:"",
                password:"",
            }
        },
        methods:{
            async signUp(){
                let result = await axios.post("http://localhost:3000/users",{
                    email:this.email,
                    password:this.password,
                    name:this.name
                })
                console.warn("sign up",this.name,this.email,this.password)
                if(result.status == 201){
                    alert("sign-up done")
                    localStorage.setItem("user-info",JSON.stringify(result.data))
                }
            }
        }
    }
</script>
<template>
    <img src="../assets/logo.png" alt="" class="logo">
    <h1>Sign Up</h1>
    <div class="register">
        <input type="text" v-model="name" placeholder="Enter name"/>
        <input type="email" v-model="email" placeholder="Enter email"/>
        <input type="password" v-model="password" placeholder="Enter password">
        <button v-on:click="signUp" >Sign Up</button>
    </div>
</template>
<style>
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
        border: 1px solid red;
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
        background: red;
        color: white;
        cursor: pointer; 
        border: none;
        font-size: large;
        border-radius: 10px;
    }
    .register button:hover{
        background: rgb(150, 36, 36);
    }
</style>
