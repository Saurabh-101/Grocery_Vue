<template>
    <HeaderPage/>
    update Restaurant
    <form action="" class="add-rest">
        <input type="text" name="name" placeholder="Resturant Name" v-model="resturant.name">
        <input type="text" name="address" placeholder="Address" v-model="resturant.address">
        <input type="text" name="contact" placeholder="Contact" v-model="resturant.contact">
        <button type="button" v-on:click="updateRest">UPDATE</button>
        
    </form>
</template>

<script>
import HeaderPage from './Header.vue';
import axios from 'axios';
export default {
    name : 'UpdateRest',
    components:{
        HeaderPage
    },
    data(){
        return{
            resturant:{
                name:'',
                address:'',
                contact:''
            }
        }
    },
    async mounted(){
        let user = localStorage.getItem('user-info');
        if(!user){
            this.$router.push({name:'SignUp'});
        }

        const result = await axios.get('http://localhost:3000/resturants/'+this.$route.params.id);
        
        this.resturant = result.data;
    },
    methods:{
        async updateRest(){
            console.log(this.resturant);
            const result = await axios.put('http://localhost:3000/resturants/'+this.$route.params.id,{
                name:this.resturant.name,
                address:this.resturant.address,
                contact:this.resturant.contact
            }) 
            if(result.status == 200){
                this.$router.push({name:'HomePage'});
            }
        }
    }
    
}
</script>