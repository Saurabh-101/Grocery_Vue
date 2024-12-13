<template>
    <HeaderPage/>
    <h1>
        add Restaurants

    </h1>

    <form action="" class="add-rest">
        <input type="text" name="name" placeholder="Resturant Name" v-model="resturant.name">
        <input type="text" name="address" placeholder="Address" v-model="resturant.address">
        <input type="text" name="contact" placeholder="Contact" v-model="resturant.contact">
        <button type="button" v-on:click="addResturant">ADD</button>
        
    </form>
</template>

<script>
import HeaderPage from './Header.vue';
import axios from 'axios';
export default {
    name: 'AddRest',
    components: {HeaderPage},
    data(){
        return{
            resturant:{
                name:'',
                address:'',
                contact:''
            }
        }
    },
    mounted(){
        let user = localStorage.getItem("user-info");
        if(!user){
            this.$router.push({name:'SignUp'});
        }
    },
    methods:{
        async addResturant(){

            const result = await axios.post("http://localhost:3000/resturants",{
                name:this.resturant.name,
                address:this.resturant.address,
                contact:this.resturant.contact  
            });
            if(result.status==201){
                this.$router.push({name:'HomePage'})
            }

        }
    }
}
</script>