<template>
  <div class="flex gap-4 h-screen">
    <!-- First column (longer) -->
    <div class="flex-4 hidden md:block">
      <img class="w-full h-full object-cover" src="../assets/medium-shot-woman-knitting-camera.jpg" alt="">
    </div>
    <!-- Second column (shorter) -->
    <div class="flex-1 p-5">
      <div class="p-5">
        <p class="text-4xl py-5">Sign In</p>
        <p class="text-xs">Welcome to Chakri Lorem ipsum dolor sit, amet consectetur adipisicing elit. Ducimus placeat officiis, laboriosam ex totam culpa. Minima magnam aliquid quae facere.</p>

        <form class="mt-10 pt-10" @submit.prevent="handleSubmit">
          <div class="mb-5">
            <label for="email" class="block mb-2 text-sm font-medium text-gray-900">Your email</label>
            <input type="email" v-model="email" id="email" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm focus:ring-blue-500 focus:border-blue-500 block w-full p-2" placeholder="name@flowbite.com" required />
          </div>
          <div class="mb-5">
            <label for="password" class="block mb-2 text-sm font-medium text-gray-900">Your password</label>
            <input type="password" v-model="password" id="password" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5" required />
          </div>

          <div class="flex items-start mb-5">
            <div class="flex items-center h-5">
              <input id="agreeTerms" v-model="agreeTerms" type="checkbox" class="w-4 h-4 border border-gray-300 rounded bg-gray-50 focus:ring-3 focus:ring-blue-300" />
            </div>
            <label for="agreeTerms" class="ms-2 text-sm font-medium text-gray-900">I agree to terms of Service</label>
          </div>
          <button type="submit" class="text-white bg-blue-800 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium text-sm w-full sm:w-auto px-5 py-4 text-center">Sign In</button>
        </form>

        <div class="mt-10 text-gray-400">
          <span>Are You New</span>
          <span class="text-blue-700 font-semibold"> Sign Up</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import axios from 'axios';
import Swal from 'sweetalert2';

const email = ref("");
const password = ref("");
const remember = ref(false);
const agreeTerms = ref(false);

const handleSubmit = () => {
  if (!agreeTerms.value) {
    Swal.fire({
      icon: 'error',
      title: 'Terms and Conditions',
      text: 'You must agree to the terms and conditions before signing in.',
    });
    return;
  }

  const formData = {
    email: email.value,
    password: password.value,
    remember: remember.value,
  };

  axios.post('http://127.0.0.1:8000/api/signin', formData)
    .then(response => {
      Swal.fire({
        icon: 'success',
        title: 'Signed In',
        text: 'You have successfully signed in!',
      });
      console.log(response.data);
      // Handle successful response
    })
    .catch(error => {
      Swal.fire({
        icon: 'error',
        title: 'Sign In Failed',
        text: error.response ? error.response.data.message : 'An error occurred. Please try again.',
      });
      console.error(error);
      // Handle error response
    });
};
</script>

<style>
/* Custom classes to match the flex ratios if needed */
.flex-4 {
  flex: 3;
}
.flex-1 {
  flex: 2;
}
</style>
