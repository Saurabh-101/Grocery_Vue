<template>
    <HeaderPage />
    <h1>Welcome Home! , {{name}}</h1>
    <table border="1px solid">
        <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Contact</th>
            <th>Address</th>
        </tr>
        <tr v-for="item in resturants" :key="item.id">
            <td>{{ item.id }}</td>
            <td>{{ item.name }}</td>
            <td>{{ item.contact }}</td>
            <td>{{ item.address }}</td>
        </tr>
    </table>
</template>

<script>
import HeaderPage from './Header.vue';
import axios from 'axios';
export default {
    name: 'HomePage',
    data(){
        return{
            name:'',
            resturants:[]
        }
    },  
    components:{
        HeaderPage,
    },
    async mounted(){
        let user = localStorage.getItem('user-info');
        this.name = JSON.parse(user).name;
        if(!user){
            this.$router.push({name:'SignUp'});
        }

        let result = await axios.get("http://localhost:3000/resturants");
        this.resturants = result.data;

    }
}
</script>

<style>
td,th{
    height: 40px;
    width: 150px;
}
</style>