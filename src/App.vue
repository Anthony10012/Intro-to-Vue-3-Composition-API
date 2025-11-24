<script setup>
import { ref } from 'vue'
import ProductDisplay from '@/components/ProductDisplay.vue'


function updateCart() {
  cart.value += 1
}
const cart = ref(0)

const premium = ref(true)

</script>
  
<template>
  <div class="nav-bar"></div>
  <div class="cart">Cart({{ cart }})</div>
  <ProductDisplay :premium="premium" @add-to-cart="updateCart"></ProductDisplay>
  
</template>

