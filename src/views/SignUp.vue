<template>
  <div class="flex gap-4 h-screen">
    <!-- First column (longer) -->
    <div class="flex-4 hidden md:block">
      <img class="w-full h-full object-cover" src="../assets/medium-shot-woman-knitting-camera.jpg" alt="">
    </div>
    <!-- Second column (shorter) just for identification -->
    <div class="flex-1 p-5">
      <div class="p-5">
        <p class="text-4xl py-5">Sign Up</p>
        <p class="text-xs">Welcome to Chakri Lorem ipsum dolor sit, amet consectetur adipisicing elit. Ducimus placeat officiis, laboriosam ex totam culpa. Minima magnam aliquid quae facere.</p>
        
        <form class="mt-10 pt-10" @submit.prevent="handleSubmit">
          <div class="mb-5">
            <label for="email" class="block mb-2 text-sm font-medium text-gray-900">Your email</label>
            <input type="email" v-model="email" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm focus:ring-blue-500 focus:border-blue-500 block w-full p-2" placeholder="name@flowbite.com" required />
          </div>
          <div class="mb-5">
            <label for="username" class="block mb-2 text-sm font-medium text-gray-900">Username</label>
            <input type="text" v-model="username" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm focus:ring-blue-500 focus:border-blue-500 block w-full p-2" placeholder="username" required />
          </div>
          <div class="mb-5">
            <label for="password" class="block mb-2 text-sm font-medium text-gray-900">Your password</label>
            <input type="password" v-model="password" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5" required />
          </div>
          <div class="flex items-start mb-5">
            <div class="flex items-center h-5">
              <input id="remember" type="checkbox" v-model="agreeTerms" class="w-4 h-4 border border-gray-300 rounded bg-gray-50 focus:ring-3 focus:ring-blue-300" required />
            </div>
            <label for="remember" class="ms-2 text-sm font-medium text-gray-900">I agree to terms of Service</label>
          </div>
          
          <button type="submit" class="text-white bg-blue-800 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium text-sm w-full sm:w-auto px-5 py-4 text-center">Create Account</button>
        </form>

        <div class="mt-10 float-bottom text-gray-400">
          <span>Already a member</span>
          <span class="text-blue-700 font-semibold"> Sign In</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import axios from 'axios';

const email = ref("");
const username = ref("");
const password = ref("");
const agreeTerms = ref(false);

const handleSubmit = () => {
  const formData = {
    email: email.value,
    username: username.value,
    password: password.value,
    agreeTerms: agreeTerms.value,
  };

  console.log(formData);
  axios.post('http://127.0.0.1:8000/api/login', formData)
    .then((result) => {
      console.log(result);
    })
    .catch((err) => {
      console.log(err);
    });
};
</script>

<style>

.flex-4 {
  flex: 3;
}
.flex-1 {
  flex: 2;
}
</style>
