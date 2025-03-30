<template>
  <div class="pricelist">
    <h2 class="text-3xl font-bold text-center text-orange-700 mb-6">
      Price List (Subject to Change)
    </h2>
    <table>
      <thead>
        <tr>
          <th>Good For (# of People)</th>
          <th>Live Weight (kg)</th>
          <th>Price (PHP)</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in priceList" :key="item.goodFor">
          <td>{{ item.goodFor }}</td>
          <td>{{ item.liveWeight }}</td>
          <td>{{ formatCurrency(item.price) }}</td>
        </tr>
      </tbody>
    </table>
    <div class="promotion">
      <p>
        <strong>Buy 1 Get Free Dinuguan or Isaw Baboy (Ready to Fry)</strong>
      </p>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const priceList = ref([
      { goodFor: 40, liveWeight: "15-17", price: 7500 },
      { goodFor: 50, liveWeight: "18-20", price: 8000 },
      { goodFor: 60, liveWeight: "21-23", price: 9000 },
      { goodFor: 80, liveWeight: "25-27", price: 9500 },
      { goodFor: 100, liveWeight: "30-33", price: 10500 },
      { goodFor: 130, liveWeight: "35-37", price: 12000 },
      { goodFor: 160, liveWeight: "40-42", price: 13500 },
      { goodFor: 200, liveWeight: "45-47", price: 15000 },
      { goodFor: 230, liveWeight: "50-53", price: 16000 },
    ]);

    const formatCurrency = (value) => {
      return `₱${value.toLocaleString()}`;
    };

    return { priceList, formatCurrency };
  },
};
</script>

<style scoped>
.pricelist {
  font-family: Arial, sans-serif;
  margin: 20px;
}

table {
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 20px;
}

th,
td {
  border: 1px solid #ddd;
  padding: 10px;
  text-align: center;
}

th {
  background-color: #f2f2f2;
}

.promotion {
  background-color: #f9f9f9;
  padding: 10px;
  border: 1px solid #ddd;
  text-align: center;
  font-weight: bold;
}

.text-orange-700 {
  color: #f97316; /* Orange color */
}
</style>
