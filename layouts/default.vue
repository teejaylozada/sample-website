<template>
  <div>
    <header class="bg-gray-900 text-white py-4 md:py-6">
      <div class="container mx-auto flex justify-between items-center px-4 md:px-6">
        <!-- Logo -->
        <div class="flex-container" @click="handleClick">
          <img src="~/assets/logo.png" alt="Logo" class="logo" />
          <div class="text-container">
              <h1 class="text-lg sm:text-lg lg:text-lg text-gray-200 font-extrabold shadow-text font-display mb-2">
                  Dental Clinic Name
              </h1>
          </div>
        </div>


        <!-- Navigation Links -->
        <ul class="hidden md:flex space-x-6 text-sm items-center justify-center font-bold">
            <li><NuxtLink to="/" class="nav-link">Home</NuxtLink></li>
            <li><NuxtLink to="/about" class="nav-link">About</NuxtLink></li>
            <li><NuxtLink to="/services" class="nav-link">Services</NuxtLink></li>
            <li><NuxtLink to="/contact-us" class="nav-link">Contact Us</NuxtLink></li>
          <li>        
            <button class="custom-button text-gray-900 hover:bg-slate-950 hover:text-white py-3 px-6 md:px-8 font-extrabold rounded transition-all transform duration-300 ease-in-out hover:shadow-xl" @click="handleClick">
              Book Appointment
            </button>
          </li>
        </ul>

      </div>
    </header>

    <div>
      <slot />
    </div>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white p-10 text-base flex flex-col footer-background">
  <OurMiniMap />
  <div class="container mx-auto grid grid-cols-12 gap-8 p-10 md:px-6">
  <!-- Column 1: About -->
  <div class="col-span-12 sm:col-span-6 lg:col-span-1 mb-8"></div>
  <div class="col-span-12 sm:col-span-6 lg:col-span-5 mb-8">
    <h1 class="text-xl font-bold mb-4">About Dectal Clinic</h1>
    <p class="text-gray-300 leading-loose">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. A esse neque quibusdam laborum, sed aut nobis sapiente dolor. Quo eveniet, quis quisquam, eius consectetur enim amet, totam quod praesentium culpa non excepturi obcaecati ad! Error necessitatibus minus unde architecto iste soluta? O
    </p>
  </div>

  <!-- Column 2: Services -->
  <div class="col-span-12 sm:col-span-6 lg:col-span-4 mb-8 ml-10">
    <h1 class="text-xl font-bold mb-4">Services</h1>
    <ul>
      <li>General Dentistry </li>
      <li>Oral Surgery and Implant Dentistry</li>
      <li>Prosthodontics</li>
      <li>Pediatric Dentistry</li>
      <li>Periodontics</li>
      <li>Endodontics</li>
      <li>Orthodontics and Clear Aligners</li>
    </ul>
  </div>

  <!-- Column 3: Website Links -->
  <div class="col-span-12 sm:col-span-12 lg:col-span-2 mb-8">
    <h1 class="text-xl font-bold mb-4">Hours</h1>
<p>Mondays to Saturdays
10 AM to 6 PM</p>
  </div>
</div>

</footer>

  </div>
</template>

<script setup lang="ts">
import OurMiniMap from "@/components/mini-map.vue"

const handleClick = () => {
  alert("Dental Clinic Name clicked!");
}

</script>

<style scoped>
  .flex-container {
    display: flex;
    align-items: center;
    cursor: pointer;
  }

  .logo {
    width: 4rem;
    height: auto;
    margin-right: 1rem;
    transition: transform 0.3s ease-in-out;
  }

  .text-container {
    max-width: 200px;
    opacity: 0;
    animation: fadeIn 0.5s ease-in-out forwards;
  }

  .flex-container:hover .logo {
    transform: scale(1.2);
  }

  .flex-container:hover .text-container {
    transform: scale(1.2);
  }

  @keyframes fadeIn {
    from {
      opacity: 0;
      transform: translateY(-10px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  .custom-button {
    background: linear-gradient(90deg, #111826 0%, #111826 50%, #d3d3d3 50%, #d3d3d3 100%);
    background-size: 200% 100%;
    background-position: right bottom;
    transition: background-position 0.5s ease;
  }

  .custom-button:hover {
    background-position: left bottom;
    background-color: #dddddd; 
    color: #dddddd; 
  }
  
  .nav-link {
    text-decoration: none;
    position: relative;
    color: #bcbcbc; /* Set the desired text color */
    font-size: 16px;
    transition: transform 0.3s, color 0.3s; /* Add a transition for a smooth effect */
  }

  .nav-link:hover {
    color: rgb(255, 255, 255); /* Set the desired hover text color */
    transform: scale(1.1); /* Set the desired scale value for the grow effect */
  }

  .nav-link::after {
    content: "";
    position: absolute;
    width: 100%;
    height: 3px;
    background-color: rgb(255, 255, 255); /* Set the desired underline color */
    bottom: 0;
    left: 0;
    
    transform-origin: bottom right;
    transform: scaleX(0); /* Initial scale for the underline */
    transition: transform 0.3s; /* Add a transition for the underline effect */
  }

  .nav-link:hover::after {
    transform-origin: bottom left;
    transform: scaleX(1); /* Scale to 1 on hover */
    
  }
</style>