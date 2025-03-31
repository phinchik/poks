<template>
  <div class="pricelist flex flex-col items-center">
    <h2 class="text-3xl font-bold text-center text-orange-700 mb-6">
      Price List (Subject to Change)
    </h2>
    <img
      :src="pricingPhoto"
      alt="Pricing List"
      class="w-full max-w-2xl rounded-lg shadow-lg"
    />
  </div>
</template>

<script>
import pricingPhoto from "@/assets/pricing.jpeg";

export default {
  setup() {
    return { pricingPhoto };
  },
};
</script>

<style scoped>
.pricelist {
  font-family: Arial, sans-serif;
  margin: 20px;
}
</style>
