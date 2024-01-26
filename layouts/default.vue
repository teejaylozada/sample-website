<template>
  <div>
    <!-- Header -->
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

        <div class="md:hidden relative" ref="dropdownContainer">
          <!-- Burger Menu Button -->
          <button @click="toggleMenu" class="text-white p-2 focus:outline-none">
            <!-- Burger Icon SVG or any other icon goes here -->
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path strokeLinecap="round" strokeLinejoin="round" strokeWidth="2" d="M4 6h16M4 12h16m-7 6h7"></path>
            </svg>
          </button>

          <!-- Dropdown Menu (Visible when the menu is open) -->
          <div v-if="isMenuOpen" ref="dropdownMenu" class="absolute right-0 mt-2 w-48 bg-white rounded-lg shadow-md z-10 border border-gray-300 overflow-hidden">
            <div class="py-1 bg-gray-900">
              <NuxtLink to="/" @click="toggleMenu" class="block px-4 py-2 text-gray-500 hover:bg-gray-100 flex items-center transition duration-300">
                <svg class="h-5 w-5 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 4h18M4 10h16M4 16h16"></path>
                </svg>
                Home
              </NuxtLink>
              <NuxtLink to="/about" @click="toggleMenu" class="block px-4 py-2 text-gray-500 hover:bg-gray-100 flex items-center transition duration-300">
                <svg class="h-5 w-5 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
                </svg>
                About
              </NuxtLink>
              <NuxtLink to="/services" @click="toggleMenu" class="block px-4 py-2 text-gray-500 hover:bg-gray-100 flex items-center transition duration-300">
                <svg class="h-5 w-5 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6"></path>
                </svg>
                Services
              </NuxtLink>
              <NuxtLink to="/contact-us" @click="toggleMenu" class="block px-4 py-2 text-gray-500 hover:bg-gray-100 flex items-center transition duration-300">
                <svg class="h-5 w-5 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8z"></path>
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3v2H9v-2l3-3V8m0 6v2"></path>
                </svg>
                Contact Us
              </NuxtLink>
            </div>
          </div>


        </div>

        <!-- Navigation Links -->
        <ul class="hidden md:flex space-x-6 text-sm items-center justify-center font-bold">
           <li><NuxtLink to="/" class="nav-link">Home</NuxtLink></li>
            <li><NuxtLink to="/about" class="nav-link">About</NuxtLink></li>
            <li><NuxtLink to="/services" class="nav-link">Services</NuxtLink></li>
            <li><NuxtLink to="/contact-us" class="nav-link">Contact Us</NuxtLink></li>
		      	<li>        
            <nuxt-link to="/about">
              <button class="custom-button text-gray-900 hover:bg-slate-950 hover:text-white py-3 px-6 md:px-8 font-extrabold rounded transition-all transform duration-300 ease-in-out hover:shadow-xl" @click="handleClick">
                  Book Appointment
                </button>
            </nuxt-link>

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
import { ref, onUnmounted } from 'vue';

const handleClick = () => {
  alert("Dental Clinic Name clicked!");
}


const isMenuOpen = ref(false);

function toggleMenu() {
  isMenuOpen.value = !isMenuOpen.value;

  if (isMenuOpen.value) {
    // Attach global click event listener to close the menu when clicking outside
    document.addEventListener('click', closeMenu);
  } else {
    // Remove the global click event listener when the menu is closed
    document.removeEventListener('click', closeMenu);
  }
}

function closeMenu(event) {
  const dropdownContainer = document.querySelector('.md\\:hidden'); // Select the dropdown menu element
  if (dropdownContainer && !dropdownContainer.contains(event.target)) {
    // Click occurred outside the dropdown, close the menu
    isMenuOpen.value = false;
  }
}

// Remove the global click event listener when the component is unmounted
onUnmounted(() => {
  document.removeEventListener('click', closeMenu);
});
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