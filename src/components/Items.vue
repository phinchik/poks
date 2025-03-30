<script setup>
import { useRouter } from "vue-router"; // Import router for redirection
import { ref } from "vue";
import pig1 from "@/assets/pokspig1.jpg";
import pig2 from "@/assets/poks1.jpg";
import pig3 from "@/assets/poksprofile.jpg";
import cow1 from "@/assets/poksbaka.jpg";
import cow2 from "@/assets/poksbaka2.jpg";
import cow3 from "@/assets/poksbaka3.jpg";

const availableItems = [
  {
    title: "Lechon Baboy (Roasted Pig)",
    description: "Crispy skin and tender meat, the best lechon in town!",
    images: [pig1, pig2, pig3], // Array of images for Lechon Baboy
    price: "₱5000",
  },
  {
    title: "Lechon Baka (Roasted Cow)",
    description: "Juicy and flavorful, perfect for big gatherings!",
    images: [cow1, cow2, cow3], // Array of images for Lechon Baka
    price: "₱10000",
  },
];

// Using router to handle redirect
const router = useRouter();
const goToPricing = () => {
  router.push("/pricing");
};
</script>

<template>
  <div class="container mx-auto px-4 py-10 max-w-full">
    <h2 class="text-3xl font-bold text-center text-orange-700 mb-6">
      Available Lechon
    </h2>
    <div class="grid gap-6 md:grid-cols-2 lg:grid-cols-2 xl:grid-cols-2">
      <div
        v-for="(item, index) in availableItems"
        :key="index"
        class="bg-white rounded-lg shadow-lg"
      >
        <!-- Carousel for Lechon -->
        <div class="relative w-full h-80 overflow-hidden">
          <!-- Scrollable images container -->
          <div class="flex transition-transform ease-in-out duration-500">
            <img
              v-for="(image, idx) in item.images"
              :key="idx"
              :src="image"
              alt="Lechon"
              class="w-full h-64 object-cover rounded-md"
            />
          </div>
        </div>

        <div class="p-6">
          <h3 class="text-2xl font-semibold text-orange-700">
            {{ item.title }}
          </h3>
          <p class="text-gray-700 mt-2">{{ item.description }}</p>
          <p class="text-lg font-bold text-green-600 mt-3">Call for Pricing</p>
          <!-- <button
            @click="goToPricing"
            class="mt-4 bg-orange-700 text-white py-2 px-4 rounded-lg hover:bg-orange-600 transition"
          >
            See Price List
          </button> -->
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* Customize card styles */
.bg-white {
  background-color: #ffffff;
}

.text-orange-700 {
  color: #f97316; /* Orange color */
}

.text-green-600 {
  color: #16a34a; /* Green color for price */
}

.text-gray-700 {
  color: #374151; /* Dark gray color */
}

.text-xl {
  font-size: 1.25rem;
}

.text-2xl {
  font-size: 1.5rem;
}

.font-semibold {
  font-weight: 600;
}

.font-bold {
  font-weight: 700;
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

.button {
  background-color: #f97316;
  color: white;
  padding: 10px;
  border-radius: 5px;
  cursor: pointer;
}

.button:hover {
  background-color: #f59e0b;
}

.w-full {
  width: 100%;
}

.h-auto {
  height: auto;
}

.object-cover {
  object-fit: cover;
}

.mt-2 {
  margin-top: 0.5rem;
}

.mt-3 {
  margin-top: 0.75rem;
}

.mt-4 {
  margin-top: 1rem;
}

.relative {
  position: relative;
}

.flex {
  display: flex;
}

.transition-transform {
  transition: transform 0.5s ease;
}

.space-x-4 {
  margin-right: 1rem;
}

.transition {
  transition: background-color 0.3s;
}

.container {
  max-width: 100%;
}

button {
  font-size: 1.5rem;
}

button:hover {
  background-color: #f97316;
}

/* Make carousel buttons float on left and right */
button {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background-color: rgba(0, 0, 0, 0.5);
  color: white;
  padding: 10px;
  border-radius: 50%;
  z-index: 1;
}
</style>
