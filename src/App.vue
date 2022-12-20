<template>
  <router-view/>
</template>

<script>
export default {
  name: 'App' 
}
</script>

<style>
body{
  padding: 0;
  margin:0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
img {
    height: 120px;
}
.register input, .SignIn input{
    width: 300px;
    height: 40px;
    padding-left: 20px;
    display: block;
    margin: 0px auto 30px auto;
    border: 1px solid #ff0047;
    border-radius: 8px;
}
.register button , .SignIn button{
    width: 150px;
    height: 40px;
    background: #ff0047;
    color: #fff;
    border: 1px solid #ff0047;
    border-radius: 8px;
    cursor: pointer;
}
</style>
