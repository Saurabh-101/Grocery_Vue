<template>
    <img src="../assets/rest-logo.png" alt="">
    <div class="login">
        <input type="text" v-model="email" placeholder="Email">
        <input type="password" v-model="password" placeholder="Password">
        <button v-on:click="login">Log In</button>
        <p> Don't have an account? 
            <router-link to="/signup">Sign Up</router-link>
        </p>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name : 'LogIn',
    data(){
        return {
            email:'',
            password:''
        }
    },
    methods:{
        async login(){
            let result = await axios.get(
                `http://localhost:3000/users?email=${this.email}&password=${this.password}`
            );
            if(result.status==200 & result.data.length>0){
                localStorage.setItem("user-info",JSON.stringify(result.data[0]));
                this.$router.push({name:'HomePage'});
            }
        }
    },
    mounted(){
        let user = localStorage.getItem("user-info");

        if(user){
            this.$router.push({name:'HomePage'});
        }
    }

}
</script>

<style>
.login input{

}
</style>