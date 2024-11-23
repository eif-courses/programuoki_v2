<script setup lang="ts">

</script>

<template>


  <UnderConstruction/>
  <!-- Main Content -->
  <div class="flex justify-center items-center flex-col space-y-8 px-6">
    <!-- Business Card Section -->
    <div class="business-card flex flex-wrap lg:flex-nowrap items-center
    space-y-4 lg:space-y-0 lg:space-x-8 p-6 rounded-lg shadow-xl border-2 border-gray-200">
      <!-- Photo Section -->
      <div class="w-full lg:w-1/3 flex justify-center">
        <img src="/me.png" alt="Your Photo" class="w-48 h-48 rounded-full shadow-lg" />
      </div>

      <!-- Info Section -->
      <div class="w-full lg:w-2/3 text-white">
        <h2 class="text-3xl font-bold mb-4 text-cyan-300">Apie Mane</h2>
        <p class="mb-2">
          Hi, I'm <strong class="text-cyan-400">Marius Gžegoževskis</strong>. This page is dedicated to showcasing my programming knowledge, tech stacks, and projects.
        </p>
        <p class="mb-4">
          I specialize in building modern, scalable web and mobile applications using frameworks like Vue, Nuxt, and .NET.
        </p>
        <ul class="space-y-2">
          <li><strong>El. Paštas:</strong> <a href="mailto:m.gzegozevskis@gmail.com" class="hover:underline text-cyan-400">m.gzegozevskis@gmail.com</a></li>
<!--          <li><strong>Phone:</strong> +123 456 7890</li>-->
          <li><strong>Location:</strong> Your City, Your Country</li>
        </ul>
      </div>
    </div>

    <!-- Highlighted Text Section -->
    <div class="text-center border-2 p-4 pb-6 border-gray-200 text-white rounded-lg shadow-xl">
      <p class="text-lg font-medium mb-4">Welcome to Programuoki.lt!</p>
      <p class="text-xl font-bold text-cyan-400 mb-4">Learn programming, explore new technologies, and build amazing projects!</p>
      <p class="text-md">This page is designed for those interested in learning and utilizing modern tech stacks. Whether you're a beginner or an experienced developer, there's always something new to discover here.</p>
    </div>
  </div>
</template>
<style scoped>
.business-card img {
  object-fit: cover;
}
</style>