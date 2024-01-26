<template>
  <div class="master h-screen flex flex-col items-center justify-center text-white text-center px-0 sm:px-10 md:px-12 lg:px-16">
    <IntroAbout />
  </div>
</template>

<script setup lang="ts">
import IntroAbout from '@/components/intro-about.vue';
</script>

<style scoped>
.master {
  background: url('~/assets/about-bg.jpg');
  background-position: center center;
  background-repeat: no-repeat;
  background-size: cover;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden; /* Add this line if you want to hide overflow */
}

/* Additional styling for IntroAbout component if needed */
/* For example, setting a max-height */
.intro-about {
  max-height: 100%; /* Adjust as needed */
}
</style>
