<template>
    <!-- <Header/> -->
    <div class="nav">
        <router-link to="/">Home</router-link>
        <router-link to="/add">Add Restaurant</router-link>
        <router-link to="update">Update Restaurant</router-link>
        <a v-on:click="logout" href="/sign-in">Logout</a>
    </div>
    <h1>Hello {{name}}!</h1>
</template>

<script>
// import Header from './Header.vue';
import axios from 'axios'
export default [{
    name:'Home',
    // components:{
    //     Header
    // },
    data(){
        return{
            name: '',
        }
    },
    methods: {
        logout(){
            localStorage.clear()
            this.$router.push({name:'SignIn'})
        }
    },
    async mounted() {
        let user = localStorage.getItem('use-info');
        this.name = JSON.parse(user).name;
        if (!user){
            this.$router.push({ name:'SignUp'})
        }   
        let result = await axios.get("http://localhost:3000/restaurant");
        console.warn(result);
    }
}]
</script>

<style>
.nav{
    background-color: #333;
    overflow: hidden;
}

.nav a{
    float: left;
    color: #f2f2f2;
    padding: 20px;
    text-align: center;
    font-size: 18px;
    margin-right: 8px;
}
.nav a:hover{
    background: #ddd;
    color:#333;
}
</style>

