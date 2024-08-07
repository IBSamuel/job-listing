<script setup></script>
<template>
  <section class="bg-white">
    <div class="py-8 px-4 mx-auto max-w-screen-xl text-center lg:py-16">
      <h1
        class="mb-4 text-4xl font-semibold tracking-tight leading-none text-gray-900 md:text-5xl lg:text-6xl"
      >
        Get The <span className="text-blue-700">Right Job</span> <br />
        You Derseve
      </h1>
      <p
        class="mb-8 text-lg font-normal text-gray-500 sm:px-16 lg:px-48 dark:text-gray-400"
      >
        1,850,570 jobs listed here! Your dream job is waiting
      </p>
      <div class="justify-center sm:space-y-0">
        <form className="">
          <div class="flex w-5/6">
            <label
              for="search-dropdown"
              class="mb-2 text-sm font-medium text-gray-900 sr-only"
              >Your Email</label
            >
            <button
              id="dropdown-button"
              data-dropdown-toggle="dropdown"
              class="flex-shrink-0 z-10 inline-flex items-center py-2 px-5 text-sm font-medium text-center bg-gray-100 border border-e-0 border-gray-300 rounded-s-full hover:bg-gray-200 focus:ring-4 focus:outline-none focus:ring-gray-300"
              type="button"
            >
              Location <i className="px-4 fa-solid fa-location-dot text-2xl"></i>
            </button>
            <div
              id="dropdown"
              class="z-10 hidden bg-white divide-y divide-gray-100 rounded-lg shadow w-44"
            >
              <ul
                class="py-2 text-sm text-gray-700"
                aria-labelledby="dropdown-button"
              >
                <li>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100"
                    >Shopping</a
                  >
                </li>
                <li>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100"
                    >Images</a
                  >
                </li>
                <li>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100">News</a>
                </li>
                <li>
                  <a href="#" class="block px-4 py-2 hover:bg-gray-100"
                    >Finance</a
                  >
                </li>
              </ul>
            </div>
            <div class="relative w-full">
              <input
                type="search"
                id="search-dropdown"
                class="block py-4 p-2.5 w-full z-20 text-sm text-gray-900 bg-gray-50 rounded-e-full rounded-s-gray-100 rounded-s-2 border border-gray-300 focus:ring-blue-500 focus:border-blue-500"
                placeholder="Job title or Key word"
                required
              />
              <button
                type="submit"
                class="absolute top-0 end-0 p-2.5 h-full text-sm font-medium text-white bg-blue-700 rounded-full px-8 border border-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300"
              >
                Search
              </button>
            </div>
          </div>
        </form>
      </div>
    </div>
  </section>
</template>
<style></style>
