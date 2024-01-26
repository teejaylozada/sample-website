<template>
  <div class="container mx-auto p-8 md:p-16 lg:p-24">
    <div class="grid grid-cols-1 md:grid-cols-12 gap-8">

      <div class="col-span-1 md:col-span-12 p-8 md:p-16 bg-gray-900 rounded-lg shadow-lg">
        <div class="grid grid-cols-1 md:grid-cols-12 gap-8">
          <div class="md:col-span-6">
            <h1 class="text-2xl md:text-4xl font-bold text-gray-300 mb-4 md:mb-6">
              About Us
            </h1>
            <p class="text-base md:text-lg text-gray-400 leading-7">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Iure asperiores aspernatur, illo vitae quibusdam suscipit ipsa laborum omnis. At facilis, nobis fuga minima molestiae rem quis cum neque iste modi voluptas ullam! Tenetur nihil, neque itaque velit distinctio veniam quibusdam soluta, dicta sit fuga ratione nostrum repellat iure architecto perferendis nam quasi iusto optio incidunt natus mollitia voluptates consequuntur obcaecati? In, tenetur error nemo ea eius atque assumenda sit officia quaerat numquam dolor, quae eaque nostrum velit. Accusantium at ipsum corporis ut odit natus blanditiis delectus a repudiandae exercitationem repellendus, beatae tenetur incidunt facilis, cupiditate vel? Aliquid eligendi repellendus necessitatibus.
            </p>
          </div>

          <div class="md:col-span-6">
            <img
              src="@/assets/about.jpg"
              alt="About Us Image"
              class="w-full h-auto rounded-lg shadow-md"
            />
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

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

.text-2xl {
  font-size: 1.5rem;
}

.text-base {
  font-size: 1rem;
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
