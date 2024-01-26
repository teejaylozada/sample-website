<template>
  <div class="p-4 text-center">
    <h1 class="text-3xl font-bold mb-4">Services</h1>
    <div class="slider-container">
      <div class="slider" :style="{ transform: 'translateX(' + -currentIndex * (310 / totalImages) + '%)' }"> 
        <div v-for="(image, index) in images" :key="index" class="slider-item">
          <div class="slider-image-container">
            <img :src="image.src" :alt="'Image ' + (index + 1)" class="slider-image">
          </div>
          <div class="slider-text-overlay">
            <h2 class="text-white text-xl font-semibold">{{ image.text.title }}</h2>
            <p class="text-white text-sm">{{ image.text.description }}</p>
          </div>
        </div>
      </div>
      <button @click="prevSlide" class="slider-button prev-button">&#10094;</button>
      <button @click="nextSlide" class="slider-button next-button">&#10095;</button>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
const images = [
  {
      src: '/project-images/1a.jpg',
      text: {
        title: 'Exhibit A ',
      },

    },
    {
      src: '/project-images/1b.jpg',
      text: {
        title: 'Exhibit B',
      },

    },
    {
      src: '/project-images/1c.jpg',
      text: {
        title: 'Exhibit C',
      },

    },
    {
      src: '/project-images/1d.jpg',
      text: {
        title: 'Exhibit D',
      },

    },
    {
      src: '/project-images/1e.jpg',
      text: {
        title: 'Exhibit E',
      },

    },
    {
      src: '/project-images/1f.jpg',
      text: {
        title: 'Exhibit F',
      },

    },
    {
      src: '/project-images/1a.jpg',
      text: {
        title: 'Exhibit 2A ',
      },

    },
    {
      src: '/project-images/1b.jpg',
      text: {
        title: 'Exhibit 2B',
      },

    },
    {
      src: '/project-images/1c.jpg',
      text: {
        title: 'Exhibit 2C',
      },

    },
    {
      src: '/project-images/1d.jpg',
      text: {
        title: 'Exhibit 2D',
      },

    },
    {
      src: '/project-images/1e.jpg',
      text: {
        title: 'Exhibit 2E',
      },

    },
    {
      src: '/project-images/1f.jpg',
      text: {
        title: 'Exhibit 2F',
      },

    },


  ];

  const totalImages = images.length;
  const currentIndex = ref(0);
  const isPaused = ref(false);
  let slideshowInterval;

  function nextSlide() {
  currentIndex.value++;
  if (currentIndex.value >= totalImages) {
    const container = document.querySelector('.slider');
    container.style.transition = 'none';
    currentIndex.value = 0;
    container.style.transform = `translateX(0%)`;
    setTimeout(() => {
      container.style.transition = 'transform 1.5s cubic-bezier(0.25, 0.46, 0.45, 0.94)';
    }, 0);
  }
  pauseSlideshow();
  setTimeout(() => resumeSlideshow(), 5000);
}

function prevSlide() {
  currentIndex.value--;
  if (currentIndex.value < 0) {
    const container = document.querySelector('.slider');
    container.style.transition = 'none';
    currentIndex.value = totalImages - 1;
    container.style.transform = `translateX(${-currentIndex.value * (100 / totalImages)}%)`;
    setTimeout(() => {
      container.style.transition = 'transform 1.5s cubic-bezier(0.25, 0.46, 0.45, 0.94)';
    }, 0);
  }
  pauseSlideshow();
  setTimeout(() => resumeSlideshow(), 5000);
}

  function startSlideshow() {
    slideshowInterval = setInterval(() => {
      if (!isPaused.value) {
        nextSlide();
      }
    }, 5000);
  }

  function pauseSlideshow() {
    isPaused.value = true;
    clearInterval(slideshowInterval);
  }

  function resumeSlideshow() {
    isPaused.value = false;
    startSlideshow();
  }

  onMounted(() => {
    startSlideshow();
  });

  onUnmounted(() => {
    clearInterval(slideshowInterval);
  });

</script>

<!-- <style scoped>
h1 {
  font-size: 2rem;
}

.slider-container {
  position: relative;
  width: 100%;
  max-width: 100%;
  margin: 0 auto;
  overflow: hidden;
}

.slider {
  display: flex;
  transition: transform 1.5s cubic-bezier(0.25, 0.46, 0.45, 0.94);
}

.slider-item {
  position: relative;
  box-sizing: border-box;
  flex: 0 0 35%;
  margin: 0px;
  border: 4px solid #fff;
  overflow: hidden;
  width: 100%; /* Set width to 100% */
  height: 40vh; /* Set the fixed height for the images */
}

.slider-image {
  width: 100%;
  height: 50vh;
  object-fit: cover; /* Ensure the image covers the entire container while preserving aspect ratio */
  border: 4px solid black;
}

.slider-text-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  height: 15vh;
  width: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center; 
  align-items: center;
  padding: 1rem;
  text-align: center;
}

.slider-button {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  font-size: 2rem;
  background-color: #333; /* Background color for the circle */
  border: none;
  color: white; /* Text color for the arrows */
  cursor: pointer;
  outline: none;
  width: 3rem; /* Width and height for the circle */
  height: 3rem;
  border-radius: 50%; /* Makes the element a circle */
  display: flex;
  justify-content: center;
  align-items: center;
}

.prev-button {
  left: 10px;
}

.next-button {
  right: 10px;
}

.slider-image {
  cursor: auto;
  transition: cursor 0.2s; /* Add a smooth transition for the cursor */
}

.slider-image:hover {
  cursor: pointer; /* Change cursor on hover */
}
.dark-background {
  background-color: #333;
  color: #fff;
}
@media (min-width: 576px) {
  .slider-item {
    flex: 0 0 45%;
    height: 30vh;
  }
}

@media (min-width: 768px) {
  .slider-item {
    flex: 0 0 30%;
    height: 40vh;
  }
}

@media (min-width: 992px) {
  .slider-item {
    flex: 0 0 30%;
    height: 50vh;
  }
}

@media (min-width: 1200px) {
  .slider-item {
    flex: 0 0 26%;
  }
}

</style> -->
