<template>
    

    <nav class="">
      <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
      <a href="https://flowbite.com/" class="flex items-center space-x-3 rtl:space-x-reverse">
          <span class="self-center text-2xl font-semibold whitespace-nowrap">
            <span className="text-blue-700">C</span>
            <span>h</span>
            <span>akr</span>
            <span className="text-blue-700">i</span>
          </span>
      </a>
      <div class="flex md:order-2 space-x-3 md:space-x-0 rtl:space-x-reverse">
          <button type="button" class="hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium  text-sm px-4 py-2 text-center hover:text-white"> <router-link to="/admin/signup">Register Now</router-link></button>
          <button type="button" class="text-blue-700 border-2 border-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium text-sm px-4 py-2 text-center"> <router-link to="/admin/signin">Log In</router-link></button>
          <button data-collapse-toggle="navbar-cta" type="button" class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500  md:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 " aria-controls="navbar-cta" aria-expanded="false">
            <span class="sr-only">Open main menu</span>
        </button>
      </div>
      <div class="items-center justify-between hidden w-full md:flex md:w-auto md:order-1" id="navbar-cta">
      </div>
      </div>
    </nav>
    
    </template>
    
    <style>
    </style>