<script>
    export default{
        name:"SignUp"
    }
</script>
<template>
    <img src="../assets/logo.png" alt="" class="logo">
    <h1>Sign Up</h1>
    <div class="register">
        <input type="text" placeholder="Enter name"/>
        <input type="email" placeholder="Enter email"/>
        <input type="password" placeholder="Enter password">
        <button>Sign Up</button>
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
