<template>
  <div class="flex justify-center items-center h-screen">
    <div class="w-1/3 bg-white rounded-lg shadow-lg p-8">
      <h2 class="text-2xl font-bold mb-4">Login</h2>
      <form @submit.prevent="login">
        <div class="mb-4">
          <label class="block text-gray-700 text-sm font-bold mb-2" for="email"
            >Email</label
          >
          <input
            v-model="email"
            type="email"
            id="email"
            class="w-full border border-gray-300 rounded-md p-2"
            required
          />
        </div>
        <div class="mb-4">
          <label
            class="block text-gray-700 text-sm font-bold mb-2"
            for="password"
            >Password</label
          >
          <input
            v-model="password"
            type="password"
            id="password"
            class="w-full border border-gray-300 rounded-md p-2"
            required
          />
        </div>
        <button
          type="submit"
          class="bg-blue-500 hover:bg-blue-600 text-white font-bold py-2 px-4 rounded"
        >
          Login
        </button>
      </form>
      don't have an account?
      <router-link
        class="inline-block align-baseline font-bold text-lg text-blue-500 hover:text-blue-800"
        :to="{ name: 'register' }"
      >
        SignUp
      </router-link>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    login() {
      axios
        .post("http://127.0.0.1:8000/login/", {
          email: this.email,
          password: this.password,
        })
        .then((response) => {
          if (response.data.success === true) {
            localStorage.setItem("userInfo", JSON.stringify(response.data));
            // alert("Login successful!");
            console.log(response.data);
            this.$router.push({ name: "home" });
          } else {
            alert(response.data.info);
            console.log(response);
          }
        })
        .catch((error) => {
          // Handle login error, e.g. display an error message
          console.error(error);
        });
    },
  },
};
</script>
