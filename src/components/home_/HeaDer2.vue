<template>
    <div>
      <div class="justify-center bg-blue-50 max-w-7xl mx-auto p-5">
        <div>
          <p class="text-center justify-center pt-20 text-4xl font-bold">
            <span>One Platform </span><br />
            <span class="text-blue-700 px-2">
              Many 
            </span>
            <span>Solutions</span>
          </p>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4 mt-8">
          <div
            v-for="(item, index) in cardsDitaillsArray"
            :key="index"
            class="w-full bg-white flex flex-cols-[2fr_1fr] py-2 gap-2 px-5 rounded-lg transition duration-700 ease-in-out hover:shadow-xl hover:bg-blue-700 hover:text-white group"
          >
            <div className="mt-4">
                              <span class="text-3xl text-red-500">{{ item.icon }}</span> <!-- Placeholder for icon -->
        </div>
            <div class="py-3">
              <p class="text-2xl font-semibold group-hover:text-white">
                {{ item.name }}
              </p>
              <p class="text-xs group-hover:text-white">
                {{ item.noOfAvailablejobs }} Jobs Available
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  const cardsDitaillsArray = [
    { name: "Marketing & Communication", icon: "📢", noOfAvailablejobs: "20" },
    { name: "Design & Development", icon: "🎨", noOfAvailablejobs: "20" },
    { name: "Human Research & Development", icon: "🧠", noOfAvailablejobs: "10" },
    { name: "Finance & Management", icon: "📈", noOfAvailablejobs: "20" },
    { name: "Armforce Guide & Security", icon: "🛡️", noOfAvailablejobs: "20" },
    { name: "Software Developer", icon: "💻", noOfAvailablejobs: "20" },
    { name: "Project Manager", icon: "📋", noOfAvailablejobs: "2" },
    { name: "Business & Consulting", icon: "📊", noOfAvailablejobs: "20" },
  ];
  </script>
  