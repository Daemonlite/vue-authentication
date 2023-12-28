<template>
    <div class="flex justify-center items-center mt-12">
      <div class="w-full max-w-[500px]">
        <form class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">

            <div class="identity-input mb-4">
            <label
              for="fullname"
              class="block text-gray-700 text-sm font-bold mb-2"
            >
              Full Name</label
            >
            <input
              id="fullname"
              class="shadow appearance-none borderrounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline"
              type="text"
              placeholder="Full Name"
              aria-describedby="fullnameHelp"
              v-model="fullname"
            />
            <span class="text-xs text-red-700" id="fullname"></span>
          </div>

            <div class="identity-input mb-4">
            <label
              for="username"
              class="block text-gray-700 text-sm font-bold mb-2"
            >
              Username</label
            >
            <input
              id="username"
              class="shadow appearance-none borderrounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline"
              type="text"
              placeholder="Username"
              aria-describedby="usernameHelp"
              v-model="username"
            />
            <span class="text-xs text-red-700" id="username"></span>
          </div>

          <div class="identity-input mb-4">
            <label
              for="phone"
              class="block text-gray-700 text-sm font-bold mb-2"
            >
              Phone Number</label
            >
            <input
              id="phone"
              class="shadow appearance-none borderrounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:shadow-outline"
              type="text"
              placeholder="phone number"
              aria-describedby="phoneHelp"
              v-model="phone"
            />
            <span class="text-xs text-red-700" id="phone"></span>
          </div>


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
              type="text"
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
              Sign up
            </button>
            
          </div>
          already have an account?
          <router-link
              class="inline-block align-baseline font-bold text-lg text-blue-500 hover:text-blue-800"
              :to="{ name: 'login' }"
            >
             Login
            </router-link>
        </form>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "SignUp",
    data() {
      return {
        email: "",
        password: "",
      };
    },
    methods: {
      signup() {
        console.log("signing up");
      },
    },
  };
  </script>
  
  