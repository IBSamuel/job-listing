<template>
    <div>
      <div>
        <p class="text-center justify-center pt-20 text-4xl font-semibold">
          <span class="text-blue-700 px-2">Featured</span>
          <span>Job Circulars</span>
        </p>
      </div>
      <div class="m-5 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4">
        <div
          v-for="(item, index) in cardsDitaillsArray"
          :key="index"
          class="flex-1 m-3 p-3 border-2 border-gray-50 rounded-lg w-60 justify-center"
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
            <div>
              <p class="font-semibold text-2xl justify-center items-center group-hover:text-white">
                Visual Designer
              </p>
              <p class="group-hover:text-white">{{ item.category }}</p>
              <br />
              <p class="group-hover:text-white">
                {{ item.s_discription }}
              </p>
            </div>
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
  </template>
  
  <script setup>
  const cardsDitaillsArray = [
    {
      companyLogo: "https://cdn-icons-png.flaticon.com/512/732/732221.png",
      name: "Microsoft",
      location: "New York",
      category: "Full-time",
      s_discription: "You will be expected to lead the company's entire UI strategy.",
      amount: 6700,
    },
    {
      companyLogo: "https://seeklogo.com/images/B/behance-logo-1373E40919-seeklogo.com.png",
      name: "Behance",
      location: "New York",
      category: "Remote",
      s_discription: "Behance.",
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
      category: "Remote",
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
      category: "Remote",
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
      category: "Remote",
      s_discription: "You will be expected to lead the company's entire UI strategy.",
      amount: 4000,
    },
  ];
  </script>
  
  <style scoped>
  /* Add any custom styles here */
  </style>
  