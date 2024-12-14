<template>
  <div class="nav">
    <router-link to="/">Home</router-link>
    <router-link to="/addrest">Add Restaurant</router-link>
    <a v-on:click="logout" href="#">Log Out</a>
  </div>
</template>

<script>
export default {
  name: "HeaderPage",
  methods:{
    logout(){
      localStorage.clear();
      this.$router.push({name:'LogIn'});
    }
  }
};
</script>

<style>
.nav {
    background: grey;
    overflow: hidden;
    
}
.nav router-link{
    float: left;
    color: whitesmoke;
    padding: 14px 16px;
    text-align: center;
    font-size: 18px;
    text-decoration: none;
    margin-right: 5px;
}
.nav a{
  float: left;
    color: whitesmoke;
    padding: 14px 16px;
    text-align: center;
    font-size: 18px;
    text-decoration: none;
    margin-right: 5px;
}
.nav a:hover{
    background-color: rgb(130, 131, 133);
    color: bisque;
}
</style>
