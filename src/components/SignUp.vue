 <template>
  <h3>Sign Up</h3>
  <div>
    <input
      type="text"
      id="name"
      v-model="username"
      class="form-group"
      placeholder="User name"
      autocomplete="off"
    />

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

    <input
      type="text"
      id="phoneno"
      v-model="phoneno"
      class="form-group"
      placeholder="Phone number"
      autocomplete="off"
    />

    <button class="btn" v-on:click="signup()">Sign up</button>
  </div>
</template>
 <script>
import axios from "axios";

export default {
  name: "SignUp",
  data() {
    return {
      username: "",
      email: "",
      password: "",
      phoneno: "",
    };
  },
  methods: {
    async signup() {
      console.warn(this.username, this.email);
      const requestdata = {
        username: this.username,
        email: this.email,
        password: this.password,
        phoneno: this.phoneno,
      };
      let result = await axios.post("http://localhost:3000/users", requestdata);

      console.log(result);
    },
  },
};
</script>
 <style>
.form-group {
  height: 40px;
  width: 300px;
  color: #4e6e8e;
  padding-left: 20px;
  display: block;
  border: 1px solid #cfd4db;
  border-radius: 0.4rem;
  font-size: 0.9rem;
  line-height: 2rem;
  margin-bottom: 30px;
  margin-left: auto;
  margin-right: auto;
}
.flex-display {
  display: flex;
  align-items: center;
}
.btn {
  display: inline-block;
  font-weight: 400;
  color: #212529;
  text-align: center;
  vertical-align: middle;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  background-color: transparent;
  border: 1px solid transparent;
  padding: 0.375rem 0.75rem;
  font-size: 1rem;
  line-height: 1.5;
  border-radius: 0.25rem;
  color: #fff;
  background-color: #28a745;
  border-color: #28a745;
}
</style>