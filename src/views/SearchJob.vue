<template>
  <NavBar/>
  <section class="bg-white">
    <div class="py-8 px-4 mx-auto max-w-screen-xl text-center lg:py-16">
      <h1 class="mb-4 text-4xl font-semibold tracking-tight leading-none text-gray-900 md:text-5xl lg:text-6xl">
        Find the <span class="text-blue-700">Perfect Job</span> <br />
        for You
      </h1>
      <p class="mb-8 text-lg font-normal text-gray-500 sm:px-16 lg:px-48">
        1,850,570 jobs listed here! Your dream job is waiting
      </p>
      <div class="justify-center sm:space-y-0">
        <form @submit.prevent="handleSearch" class="w-5/6 mx-auto flex">
          <div class="relative w-full">
            <input
              type="search"
              v-model="searchKeyword"
              class="block py-4 p-2.5 w-full z-20 text-sm text-gray-900 bg-gray-50 rounded-e-full border border-gray-300 focus:ring-blue-500 focus:border-blue-500"
              placeholder="Job title or Keyword"
              required
            />
            <button
              type="submit"
              class="absolute top-0 end-0 p-2.5 h-full text-sm font-medium text-white bg-blue-700 rounded-full px-8 border border-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300"
            >
              Search
            </button>
          </div>
        </form>
      </div>
    </div>
  </section>

  <div>
    <div>
      <p class="text-center justify-center pt-20 text-4xl font-semibold">
        <span class="text-blue-700 px-2">Featured</span>
        <span>Job Circulars</span>
      </p>
    </div>
    <div class="max-w-7xl justify-center mx-auto p-5 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4">
      <div
        v-for="(item, index) in filteredCards"
        :key="index"
        class="flex-1 m-3 p-3 border-2 border-gray-50 rounded-lg w-72 mt-3 justify-center"
      >
        <div class="mb-8 pb-4 flex items-center">
          <img
            :src="item.companyLogo"
            alt=""
            class="rounded-3xl w-20 h-20"
          />
          <div class="ml-2">
            <span class="block text-3xl font-semibold group-hover:text-white">{{ item.name }}</span>
            <span class="font-medium text-xl align-top">{{ item.location }}</span>
          </div>
        </div>
        <div>
          <p class="font-semibold text-2xl justify-center items-center group-hover:text-white">
            {{ item.jobtitle }}
          </p>
          <p class="group-hover:text-white">{{ item.category }}</p>
          <br />
          <p class="group-hover:text-white">
            {{ item.s_discription }}
          </p>
        </div>
        <div>
          <div class="my-7 flex">
            <p class="font-semibold text-xl mt-20 align-middle group-hover:text-white">
              <span>$</span>
              <span>{{ item.amount }}</span>
            </p>
            <p
              class="ms-8 text-blue-800 rounded-lg bg-blue-100 py-2 px-4 font-semibold hover:bg-blue-700 hover:text-white"
            >
              Apply Now
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>

  <Footer/>
</template>

<script setup>
import { ref, computed } from 'vue';

import NavBar from '@/components/admin/Navbar.vue';
import HeaDer from '@/components/HeaDer.vue';
import Footer from '@/components/FooterPage.vue';

const cardsDitaillsArray = ref([
  {
    companyLogo: "https://cdn-icons-png.flaticon.com/512/732/732221.png",
    name: "Microsoft",
    location: "New York",
    category: "Full-time",
    jobtitle:"Web Developer",
    s_discription: "You will be expected to lead the company's entire UI strategy.",
    amount: 6700,
  },
  {
    companyLogo: "https://seeklogo.com/images/B/behance-logo-1373E40919-seeklogo.com.png",
    name: "Behance",
    location: "New York",
    category: "Remote",
    jobtitle:"Cyber Security",
    s_discription: "Behance.",
    amount: 4000,
  },
  {
    companyLogo: "https://seeklogo.com/images/B/behance-logo-1373E40919-seeklogo.com.png",
    name: "Behance",
    location: "New York",
    category: "Remote",
    jobtitle:"Web Developher",
    s_discription: "You will be expected to lead the company's entire UI strategy.",
    amount: 4000,
  },
  {
    companyLogo: "https://seeklogo.com/images/B/behance-logo-1373E40919-seeklogo.com.png",
    name: "Behance",
    location: "Good Looks",
    category: "Remote",
    jobtitle:"Hair Dresser",
    s_discription: "You will be expected to lead the company's entire UI strategy.",
    amount: 4000,
  },
  {
    companyLogo: "https://seeklogo.com/images/B/behance-logo-1373E40919-seeklogo.com.png",
    name: "Behance",
    location: "New York",
    category: "Remote",
    s_discription: "You will be expected to lead the company's entire UI strategy.",
    amount: 4000,
  },
  {
    companyLogo: "https://seeklogo.com/images/B/behance-logo-1373E40919-seeklogo.com.png",
    name: "Behance",
    location: "New York",
    jobtitle:"Graphic Designer",
    category: "Remote",
    s_discription: "You will be expected to lead the company's entire UI strategy.",
    amount: 4000,
  },
  {
    companyLogo: "https://seeklogo.com/images/B/behance-logo-1373E40919-seeklogo.com.png",
    name: "SQI",
    jobtitle:"Laravel Developer",
    location: "New York",
    category: "Remote",
    s_discription: "You will be expected to lead the company's entire UI strategy.",
    amount: 4000,
  },
  {
    companyLogo: "https://seeklogo.com/images/B/behance-logo-1373E40919-seeklogo.com.png",
    name: "Hand$ome",
    jobtitle:"Socia Media Marketer",
    location: "New York",
    category: "Remote",
    s_discription: "You will be expected to lead the company's entire UI strategy.",
    amount: 4000,
  },
]);

const searchKeyword = ref("");

const filteredCards = computed(() => {
  return cardsDitaillsArray.value.filter(card => 
    card.jobtitle && card.jobtitle.toLowerCase().includes(searchKeyword.value.toLowerCase())
  );
});

const handleSearch = () => {
  // You can add additional logic here if needed
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
