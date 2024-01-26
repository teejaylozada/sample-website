<template>
  <!--HOME -->
<div class="mastering-metal h-screen flex flex-col items-center justify-center text-white text-center px-0 sm:px-10  md:px-12 lg:px-16">
  <h1 class="mb-4 text-5xl sm:text-6xl lg:text-7xl sm:px-14 lg:px-32 xl:px-40 2xl:px-72 font-extrabold shadow-text font-display mb-10">
      Dental Clinic Name...
  </h1>
  <p class="text-lg md:text-xl justify-center text-center mb-10 px-10 sm:px-14 lg:px-32 xl:px-40 2xl:px-72 mt-10">
      Dental Clinic qoute ........<br>
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quo officiis exercitationem aliquid deserunt eligendi ut quos ex! Aut rem voluptatum commodi assumenda dolorum aspernatur? Id laboriosam natus recusandae dignissimos facere mollitia. Odio, incidunt explicabo animi minus non rerum impedit enim temporibus neque ipsum sequi, obcaecati saepe quod soluta quo dolor. 
  </p>
  <button class="custom-button text-gray-900 hover:bg-gray-900 hover:text-white py-3 px-6 md:px-8 font-extrabold rounded transition-all transform duration-300 ease-in-out hover:shadow-xl" @click="handleClick">
      Book Now
  </button>
</div>
<div class="flex flex-col items-center justify-center text-white text-center px-0 sm:px-10  md:px-12 lg:px-16 my-12">
  <h1 class="mb-4 text-5xl sm:text-6xl lg:text-7xl sm:px-14 lg:px-32 xl:px-40 2xl:px-72 font-extrabold shadow-text font-display mb-10 text-gray-900">
      Welcome to Dental Clinic Name
  </h1>
  <p class="text-lg md:text-xl justify-center text-center mb-10 px-10 sm:px-14 lg:px-32 xl:px-40 2xl:px-72 mt-10 text-gray-900">
      Dental clinic <br>
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quo officiis exercitationem aliquid deserunt eligendi ut quos ex! Aut rem voluptatum commodi assumenda dolorum aspernatur? Id laboriosam natus recusandae dignissimos facere mollitia. Odio, incidunt explicabo animi minus non rerum impedit enim temporibus neque ipsum sequi, obcaecati saepe quod soluta quo dolor. 
  </p>
</div>
<Slider />
<IntroAbout />
</template>
<script setup>
import Slider from '@/components/slider.vue';
import IntroAbout from '@/components/intro-about.vue';
const handleClick = () => {
  alert("Book Now clicked!");
}

</script>

<style scoped>
html, body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.mastering-metal {
  background: url('~/assets/download.jpg');
  background-position: center center;
  background-repeat: no-repeat;
  background-size: cover;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  position: relative;
}
.custom-button {
    background: linear-gradient(90deg, #111826 0%, #111826 50%, #fff 50%, #fff 100%);
    background-size: 200% 100%;
    background-position: right bottom;
    transition: background-position 0.5s ease;
  }

  .custom-button:hover {
    background-position: left bottom;
    background-color: #e5e1e1; 
    color: #dddddd; 
  }
</style>
