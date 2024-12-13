<template>
    <HeaderPage/>
    <h1>
        add Restaurants

    </h1>
</template>

<script>
import HeaderPage from './Header.vue';
export default {
    name: 'AddRest',
    components: {HeaderPage},
    mounted(){
        let user = localStorage.getItem("user-info");
        if(!user){
            this.$router.push({name:'SignUp'});
        }
    }
}
</script>