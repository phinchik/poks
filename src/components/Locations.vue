<script setup>
const locations = [
  {
    title: "Apalit Branch",
    location: "McArthur Highway, Sampaloc, Apalit, Pampanga",
    locationDescription:
      "In front of 7/11 / KFC / Premier Hospital - Beside Larlyn Village 2016, Apalit, Philippines",
    facebook: "https://www.facebook.com/profile.php?id=100057584733698",
    phone: "09777383262",
    mapEmbed:
      "https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3854.579062927922!2d120.75545677587577!3d14.96052708556964!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3396563352dac01f:0x304d9cf80f8866ef!2sPok's%20Lechon%20House%20-%20Apalit%20%2CPampanga!5e0!3m2!1sen!2sus!4v1743371078264!5m2!1sen!2sus",
  },
  {
    title: "Mexico Branch",
    location: "3PFW+5VC, Jose Abad Santos Ave, Mexico, Pampanga, Philippines",
    locationDescription: "Near Pelco 1 Station",
    facebook: "https://www.facebook.com/profile.php?id=61573080839653",
    phone: "09531461747",
    mapEmbed:
      "https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3852.550884329115!2d120.74461257587743!3d15.072937485471313!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3396fb91f31be145:0x947e3416ca366d1!2sPok's%20Lechon%20House%20-%20Mexico%20Pampanga!5e0!3m2!1sen!2sus!4v1743371218107!5m2!1sen!2sus",
  },
];
</script>

<template>
  <div class="container mx-auto px-4 py-10 grid gap-6 md:grid-cols-2">
    <div
      v-for="(location, index) in locations"
      :key="index"
      class="bg-white shadow-lg rounded-2xl overflow-hidden border border-gray-200 transition-transform hover:scale-105"
    >
      <div class="p-6">
        <h3 class="text-2xl font-bold text-orange-700 mb-2">
          {{ location.title }}
        </h3>
        <p class="text-gray-700 font-medium">{{ location.location }}</p>
        <p class="text-sm text-gray-500 mb-3">
          {{ location.locationDescription }}
        </p>

        <div class="mt-4 flex flex-col space-y-3">
          <a
            :href="location.facebook"
            target="_blank"
            class="bg-blue-600 text-white px-4 py-2 rounded-md text-center hover:bg-blue-700 transition"
          >
            Visit on Facebook
          </a>
          <a
            :href="'tel:' + location.phone"
            class="bg-green-600 text-white px-4 py-2 rounded-md text-center hover:bg-green-700 transition"
          >
            Call: {{ location.phone }}
          </a>
        </div>
      </div>

      <!-- Google Maps Embed -->
      <div class="relative w-full h-64">
        <iframe
          class="absolute top-0 left-0 w-full h-full rounded-b-2xl"
          :src="location.mapEmbed"
          style="border: 0"
          allowfullscreen=""
          loading="lazy"
          referrerpolicy="no-referrer-when-downgrade"
        ></iframe>
      </div>
    </div>
  </div>
</template>
