<template>
    <img src ="../assets/resto.png" alt="img"/>
    <h1>Sign In</h1>
    <div class="SignIn">
        <input type="text" v-model="email" placeholder="Enter Email"/>
        <input type="password" v-model="password" placeholder="Enter Password"/>
        <button v-on:click="SignIn">Sign In</button>
        <p>
            <router-link to="/sign-up">Sign Up</router-link>
        </p>
    </div>
</template>

<script>
import axios from 'axios'
export default ({
    name: 'SignIn',
    data(){
        return{
            email:'',
            password:''
        }
    },
    methods:{
        async SignIn(){
            let result = await axios.get(`http://localhost:3000/users?email=${this.email}&password=${this.password}`)
            if(result.status == 200 && result.data.length > 0){
                localStorage.setItem("use-info",JSON.stringify(result.data[0]));
                this.$router.push({ name:'Home'})
            }
            console.warn(result)
        }
    },
    mounted() {
        let user = localStorage.getItem('use-info');
        if (user){
            this.$router.push({ name:'Home'})
        }   
    }
})
</script>

