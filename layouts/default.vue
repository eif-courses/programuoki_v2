<script setup lang="ts">
const isOpen = ref(false);
</script>

<template>
  <div class="container">
    <!-- Navigation Bar -->
    <nav
        class="relative mx-auto mt-4 w-3/4 max-w-5xl flex flex-wrap items-center justify-between p-4 bg-cyan-600  rounded-lg shadow-lg z-20"
    >
      <!-- Logo and Title -->
      <div class="flex items-center space-x-3">
        <img src="../../logo.png" alt="logo" class="w-14" />
        <div class="text-white text-2xl font-bold">Programuoki.lt</div>
      </div>

      <!-- Hamburger Menu (Small Screens) -->
      <button
          class="lg:hidden text-white text-xl focus:outline-none"
          @click="isOpen = !isOpen"
      >
        ☰
      </button>

      <!-- Navigation Links -->
      <div
          :class="{'hidden': !isOpen, 'block': isOpen}"
          class="w-full lg:flex lg:w-auto lg:space-x-4 lg:items-center"
      >
        <button
            @click="navigateTo('/')"
            class="block w-full bg-cyan-800 lg:w-auto lg:inline-block p-3 rounded-lg text-white hover:bg-gray-800"
        >
          Pagrindinis
        </button>
        <button
            class="block w-full lg:w-auto lg:inline-block p-3 rounded-lg text-white hover:bg-gray-800"
        >
          Mano Projektai
        </button>
        <button @click="navigateTo('/lectures')"
            class="block w-full lg:w-auto lg:inline-block p-3 rounded-lg text-white hover:bg-gray-800"
        >
          Pamokos
        </button>
      </div>
    </nav>

    <!-- Main Content -->
    <div class="main-content-container mx-auto mt-8 w-3/4 max-w-5xl p-6
    rounded-lg shadow-lg overflow-auto h-[calc(100vh-200px)]">
      <slot />
    </div>
  </div>
</template>

<style scoped>

</style>
