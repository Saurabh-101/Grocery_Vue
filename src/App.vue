<template>

<router-view />

</template>

<script>
export default {
  name: 'App',
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  
}
body{
  margin: 0;
  padding: 0;
}
.logo {
  width: 100px;
}
.reg input, .login input, .add-rest input {
  width: 300px;
  height: 40px;
  padding-left: 20px;
  display: block;
  margin : 10px auto 30px auto ;
  
  border: 1px solid orange;
}
.reg button, .login button, .add-rest button{
  width: 320px;
  height: 40px;
  border: 1px solid orange;
  background-color: orange;
  color: whitesmoke;
  cursor: pointer;
}
</style>
