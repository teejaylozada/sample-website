<template>
  <div class="container mx-auto p-16">
    <div class="grid grid-cols-10 gap-8">
      <div class="col-span-2"></div>

      <div class="col-span-6 p-16 bg-gray-200 rounded-lg shadow-lg">
        <div class="grid grid-cols-2 gap-8">
          <div class="col-span-1">
            <h1 class="text-4xl font-bold text-gray-800 mb-6">
              About Us
            </h1>
            <p class="text-lg text-gray-700 leading-7">
              Lorem ipsum dolor sit amet consectetur adipisicing elit.
              Eius quis voluptate tenetur porro facere consequatur adipisci
              nulla! Eaque rerum quas quasi illum odit optio, tempore
              aliquid consequuntur?
              Lorem ipsum dolor sit amet consectetur adipisicing elit.
              Eius quis voluptate tenetur porro facere consequatur adipisci
              nulla! Eaque rerum quas quasi illum odit optio, tempore
              aliquid consequuntur?
              Lorem ipsum dolor sit amet consectetur adipisicing elit.
              Eius quis voluptate tenetur porro facere consequatur adipisci
              nulla! Eaque rerum quas quasi illum odit optio, tempore
              aliquid consequuntur?
            </p>
            <div class="mt-10">
              <button class="custom-button text-gray-900 hover:text-white py-3 px-6 md:px-8 font-extrabold rounded        transition-all transform duration-300 ease-in-out hover:shadow-xl">
                Learn more..
            </button>
            </div>

          </div>

          <div class="col-span-1">
            <img
              src="@/assets/about.jpg"
              alt="About Us Image"
              class="w-full h-auto rounded-lg shadow-md"
            />
          </div>
        </div>
      </div>

      <div class="col-span-2"></div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
.container {
  max-width: 1800px;
}

.grid {
  margin: 0 auto;
}

.bg-gray-200 {
  background-color: #f0f4f8;
}

.rounded-lg {
  border-radius: 1rem;
}

.shadow-lg {
  box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
}

.text-4xl {
  font-size: 2.5rem;
}

.text-lg {
  font-size: 1.25rem;
}

.leading-7 {
  line-height: 1.7;
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
