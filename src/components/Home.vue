<template>
    <HeaderPage />
    <h1>Welcome Home!</h1>
    <a href=""></a>
</template>

<script>
import HeaderPage from './Header.vue';
export default {
    name: 'HomePage',
    components:{
        HeaderPage,
    },
    mounted(){
        let user = localStorage.getItem('user-info');
        if(!user){
            this.$router.push({name:'SignUp'});
        }
    }
}
</script>