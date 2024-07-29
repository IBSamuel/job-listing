<template>
    <div class="flex gap-4 h-screen">
      <!-- First column (longer) -->
      <div class="flex-4 border">
       <img class="w-screen" src="../assets\medium-shot-woman-knitting-camera.jpg" alt="">
      </div>
      <!-- Second column (shorter) -->
      <div class="flex-1 border p-5">
        <div className="p-5">
            <p className="text-4xl py-5">Sign up</p>
            <p className="text-xs">Welcome to Chakri Lorem ipsum dolor sit, amet consectetur adipisicing elit. Ducimus placeat officiis, laboriosam ex totam culpa. Minima magnam aliquid quae facere. </p>

            

<form class=" mt-10 pt-10">
  <div class="mb-5">
    <label for="email" class="block mb-2 text-sm font-medium text-gray-900 ">Your email</label>
    <input type="email" id="email" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm focus:ring-blue-500 focus:border-blue-500 block w-full p-2" placeholder="name@flowbite.com" required />
  </div>
  <div class="mb-5">
    <label for="password" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Your password</label>
    <input type="password" id="password" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 " required />
  </div>
  <div class="flex items-start mb-5">
    <div class="flex items-center h-5">
      <input id="remember" type="checkbox" value="" class="w-4 h-4 border border-gray-300 rounded bg-gray-50 focus:ring-3 focus:ring-blue-300 dark:bg-gray-700 dark:border-gray-600 dark:focus:ring-blue-600 dark:ring-offset-gray-800 dark:focus:ring-offset-gray-800" required />
    </div>
    <label for="remember" class="ms-2 text-sm font-medium text-gray-900 dark:text-gray-300">I agree to terms of Service</label>
  </div>
  <p type="submit" class="text-white bg-blue-800 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium text-sm w-full sm:w-auto px-5 py-4 text-center">Create Account</p>
</form>

<div className="mt-10 float-bottom  text-gray-400">
  
    <span>Already a memeber</span>
    <span className="text-blue-700 font-semibold"> Sign In</span>
</div>
        </div>
      </div>
    </div>
  </template>

<script setup>
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
  