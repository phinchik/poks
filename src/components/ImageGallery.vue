<script setup>
import image1 from "@/assets/pig1.jpg";
import image2 from "@/assets/pig2.jpg";
import image3 from "@/assets/pig3.jpg";
import image4 from "@/assets/pig4.jpeg";
import image5 from "@/assets/pig5.jpeg";
import image6 from "@/assets/pigchop1.jpeg";
import image7 from "@/assets/location1.png";
import image8 from "@/assets/pig7.jpeg";

const galleryImages = [
  image1,
  image2,
  image3,
  image4,
  image5,
  image6,
  image7,
  image8,
];
</script>

<template>
  <div class="container mx-auto px-4 py-10 max-w-full">
    <h2 class="text-3xl font-bold text-center text-orange-700 mb-6">
      Image Gallery
    </h2>
    <div
      class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6"
    >
      <div
        v-for="(image, index) in galleryImages"
        :key="index"
        class="bg-white rounded-lg shadow-lg overflow-hidden border border-gray-200"
      >
        <img
          :src="image"
          alt="Gallery Image"
          class="w-full h-64 object-cover"
        />
      </div>
    </div>
  </div>
</template>

<style scoped>
/* Customize gallery styles */
.bg-white {
  background-color: #ffffff;
}

.text-orange-700 {
  color: #f97316; /* Orange color */
}

.rounded-lg {
  border-radius: 0.5rem;
}

.shadow-lg {
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.border {
  border-width: 1px;
}

.border-gray-200 {
  border-color: #e5e7eb;
}

.w-full {
  width: 100%;
}

.h-64 {
  height: 16rem;
}

.object-cover {
  object-fit: cover;
}
</style>
