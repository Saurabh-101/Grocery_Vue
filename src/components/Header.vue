<template>
  <div class="nav">
    <a href="#">Home</a>
    <a href="#">Add Restaurant</a>
    <a href="#">Update Restaurants</a>
    <a href="#">Log Out</a>
  </div>
</template>

<script>
export default {
  name: "HeaderPage",
};
</script>

<style>
.nav {
    background: grey;
    overflow: hidden;
    
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
