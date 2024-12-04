<template>
    <h1>Welcome Home!</h1>
    <a href=""></a>
</template>

<script>
export default {
    name: 'HomePage',
    mounted(){
        let user = localStorage.getItem('user-info');
        if(!user){
            this.$router.push({name:'SignUp'});
        }
    }
}
</script>