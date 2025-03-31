<script setup>
import feedback1 from "@/assets/review1.jpg";
import feedback2 from "@/assets/review2.jpg";

const feedbackList = [
  {
    image: feedback1,
  },
  {
    image: feedback2,
  },
];
</script>

<template>
  <div class="container mx-auto px-4 py-10 max-w-full">
    <h2 class="text-3xl font-bold text-center text-orange-700 mb-6">
      Customer Feedback
    </h2>
    <div class="flex flex-wrap justify-center gap-6">
      <div
        v-for="(feedback, index) in feedbackList"
        :key="index"
        class="bg-white rounded-lg shadow-lg overflow-hidden border border-gray-200 flex justify-center items-center w-96"
      >
        <img
          :src="feedback.image"
          alt="Customer feedback"
          class="w-full h-96 object-cover"
        />
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

.text-gray-700 {
  color: #374151; /* Dark gray color */
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

.h-96 {
  height: 24rem;
}

.object-cover {
  object-fit: cover;
}
</style>
