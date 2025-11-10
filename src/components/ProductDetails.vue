<template>
  <div class="product-details">
    <h3>Product Details:</h3>
    <ul>
      <li v-for="(detail, index) in details" :key="index">{{ detail }}</li>
    </ul>
  </div>
</template>


<script setup>
import { defineProps } from 'vue'

const props = defineProps({
  details: {
    type: Array,
    required: true
  }
})
</script>

<style scoped>
.product-details ul {
  padding-left: 20px;
}
</style>