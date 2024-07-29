<template>
  <div>
    <div>
      <p class="text-center justify-center pt-20 text-4xl font-semibold">
        <span class="text-blue-700 px-2">Featured</span>
        <span>Job Circulars</span>
      </p>
    </div>
    <div class="max-w-7xl mx-auto p-5 h-screen overflow-y-auto">
      <div class="flex flex-col items-center">
        <div
          v-for="(item, index) in cardsDitaillsArray"
          :key="index"
          class="flex-1 m-3 p-3 border-2 border-gray-50 rounded-lg w-72 mt-3"
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
  </div>
</template>

  
  <script setup>
  import { ref, onMounted, onUnmounted } from 'vue';
  
  const testimonials = ref([
    {
      name: "Samuel Fame",
      image: "https://flowbite.s3.amazonaws.com/blocks/marketing-ui/avatars/michael-gouch.png",
      testimony: "Chakri is just awesome. It contains tons of predesigned components and pages starting from the login screen to complex dashboard. Perfect choice for your next SaaS application.",
      position: "Google Chairman",
    },
    {
      name: "Michael Gough",
      image: "https://flowbite.s3.amazonaws.com/blocks/marketing-ui/avatars/michael-gouch.png",
      testimony: "Using Chakri has been a game-changer for our team. The ease of use and the rich components available saved us a lot of time.",
      position: "CEO at Google",
    },
    {
      name: "Jane Doe",
      image: "https://flowbite.s3.amazonaws.com/blocks/marketing-ui/avatars/michael-gouch.png",
      testimony: "I found the perfect job through Chakri. The platform is user-friendly and has a vast network of job opportunities.",
      position: "Product Manager at Microsoft",
    }
  ]);
  
  const currentTestimonialIndex = ref(0);
  
  const currentTestimonial = computed(() => testimonials.value[currentTestimonialIndex.value]);
  
  onMounted(() => {
    const interval = setInterval(() => {
      currentTestimonialIndex.value = (currentTestimonialIndex.value + 1) % testimonials.value.length;
    }, 3000);
  
    onUnmounted(() => {
      clearInterval(interval);
    });
  });
  </script>
  <style scoped>
  .max-w-7xl {
    max-width: 100%;
  }
  .h-screen {
    height: 100vh;
  }
  .overflow-y-auto {
    overflow-y: auto;
  }
  </style>
  
  
  