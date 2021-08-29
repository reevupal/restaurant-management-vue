<template>
<div style="margin-top: 10rem">
  <img alt="Vue logo" src="../assets/logo-rest.png" style="height: 200px;"/>
  <h3>Login</h3>
  <div>
    <input
      type="text"
      id="email"
      v-model="email"
      class="form-group"
      placeholder="Email address"
      autocomplete="off"
    />

    <input
      type="password"
      id="password"
      v-model="password"
      class="form-group"
      placeholder="Password"
      autocomplete="off"
    />
  </div>
  <button class="btn" v-on:click="login()">Login</button>
</div>

</template>

<script>
import axios from "axios";

export default {
  name: 'Login',
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods:{
      async login(){
          let result = await axios.get(`http://localhost:3000/users?email=${this.email}&password=${this.password}`
          );

          if(result.status == 200 && result.data.length > 0){
              localStorage.setItem('user-info',JSON.stringify(result.data[0]));
              this.$router.push({ name: 'Home' })
          }
      },

  },
  
      mounted(){
        let userDetails= localStorage.getItem('user-info');

        if(userDetails){
            this.$router.push({ name: 'Home' });
        }
      }

};
</script>
<style>
</style>