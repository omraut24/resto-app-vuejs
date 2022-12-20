<template>
    <!-- <Header/> -->
    <div class="nav">
        <router-link to="/">Home</router-link>
        <router-link to="/add">Add Restaurant</router-link>
        <router-link to="update">Update Restaurant</router-link>
        <a v-on:click="logout" href="/sign-in">Logout</a>
    </div>
    <h1>Hello folks! Add restaurant Data</h1>
</template>

<script>
// import Header from './Header.vue';
export default [{
    name:'Add',
    // components:{
    //     Header
    // },
    
    mounted() {
        let user = localStorage.getItem('use-info');
        if (!user){
            this.$router.push({ name:'SignUp'})
        }   
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

