<script setup>
import { defineProps } from "vue";
import backgroundImg from "@/assets/poks1.jpg";

defineProps({
  title: {
    type: String,
    default: "Pok's Lechon House",
  },
  subtitle: {
    type: String,
    default: "Sarap ng Tunay na Lechon, Tikman sa Pok’s Lechon House!",
  },
});
</script>

<template>
  <!-- Hero Section -->
  <section
    class="relative py-20 mb-4 bg-cover bg-center bg-no-repeat"
    :style="{ backgroundImage: `url(${backgroundImg})` }"
  >
    <!-- Full-width black overlay -->
    <div class="absolute inset-0 bg-black bg-opacity-50"></div>

    <div
      class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col items-center"
    >
      <div class="text-center">
        <h1 class="text-4xl font-extrabold text-white sm:text-5xl md:text-6xl">
          {{ title }}
        </h1>
        <p class="my-4 text-xl text-white">
          {{ subtitle }}
        </p>
      </div>
    </div>
  </section>
</template>
