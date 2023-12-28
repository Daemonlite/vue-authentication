<template>
    <div class="flex justify-center items-center mt-32">
      <div class="w-full max-w-[400px]">
        <form class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4" @submit.prevent="login">
          <div class="identity-input mb-4">
            <label
              for="identity"
              class="block text-gray-700 text-sm font-bold mb-2"
            >
              Email</label
            >
            <input
              id="identity"
              class="shadow appearance-none borderrounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline"
              type="email"
              placeholder="Email"
              aria-describedby="emailHelp"
              v-model="email"
            />
            <span class="text-xs text-red-700" id="emailHelp"></span>
          </div>

  
          <div class="password-input mb-6">
            <label
              for="identity"
              class="block text-gray-700 text-sm font-bold mb-2"
              >Password</label
            >
  
            <input
              aria-describedby="passwordHelp"
              v-model="password"
  
              class="shadow appearance-none borderrounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline"
              id="password"
              type="password"
              placeholder="*******"
            />
  
            <span class="text-xs text-red-700" id="passwordHelp"></span>
          </div>
  
          <div class="flex items-center justify-between">
            <button
              class="bg-blue-600 hover:bg-black text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
              type="submit"
            >
              Sign In
            </button>
            <a
              class="inline-block align-baseline font-bold text-sm text-blue-500 hover:text-blue-800"
              href="#"
            >
              Forgot Password?
            </a>
          </div>
          dont have an account?
          <router-link
              class="inline-block align-baseline font-bold text-md text-blue-500 hover:text-blue-800 mt-4"
              :to="{ name: 'register' }"
            >
             SignUp
            </router-link>
        </form>
        
      </div>
    </div>
  </template>
  
  <script>
import axios from 'axios';
import { useRouter } from 'vue-router';
import { ref } from 'vue';

export default {
  setup() {
    const router = useRouter();
    const email = ref('');
    const password = ref('');

    const login = async () => {
      
      try {
        const response = await axios.post('http://localhost:4000/api/users/login/', {
          email: email.value,
          password: password.value
        });

        console.log(response.data);
        localStorage.setItem('token', response.data.token);
        alert('Login successful');
        router.push({ name: 'home' });
      } catch (error) {
        console.error(error);
      }
    };

    return {
      email,
      password,
      login
    };
  }
};
</script>
  