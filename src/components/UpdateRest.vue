<template>
    <HeaderPage/>
    update Restaurant
</template>

<script>
import HeaderPage from './Header.vue';
export default {
    name : 'UpdateRest',
    components:{
        HeaderPage
    },
    mounted(){
        let user = localStorage.getItem('user-info');
        if(!user){
            this.$router.push({name:'SignUp'});
        }
    }
    
}
</script>