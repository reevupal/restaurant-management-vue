<template>
   <div>
       <ul>
  <li><a class="active" href="#home">Home</a></li>
  <li><a href="#">Add Restaurant</a></li>
  <li><a href="#">Update Restaurant</a></li>
  <li><a href="#" v-on:click="logout()">Log Out</a></li>
</ul>
   </div>
</template>
<script>
export default {
    name: "Header",
    methods:{
        logout(){
            localStorage.clear();
            this.$router.push({name : 'Login'});
        }
    }
}
</script>
<style>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #333;
}

li {
  float: left;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover {
  background-color: rgb(34, 145, 111);
}
</style>