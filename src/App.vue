<script setup>
import { ref } from 'vue'
import ProductDisplay from '@/components/ProductDisplay.vue'

const cart = ref(0)
const premium = ref(true)

function updateCart() {
  cart.value += 1
}

function RemoveCart() {
  if (cart.value > 0){
    cart.value -=1
  }
}
</script>
  
<template>
  <div class="nav-bar"></div>
  <div class="cart">Cart({{ cart }})</div>
  <ProductDisplay :premium="premium" @add-to-cart="updateCart" @remove-to-cart="RemoveCart"></ProductDisplay>
</template>