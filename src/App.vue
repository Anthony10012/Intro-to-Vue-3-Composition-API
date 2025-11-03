<script setup>
import { ref } from 'vue'
import socksGreenImage from './assets/images/socks_green.jpeg'

const product = ref('Socks')
const image = ref(socksGreenImage)
const inStock = true
const details = ref(['50% coton', '30% laine', '20% polyester'])
const variants = ref([{id:2234, color:"green"},{id:2235, color:"blue"},])
const sizes = ref(["S","M","L","XL",])
</script>
  
<template>
  <div class="nav-bar"></div>
  <div class="product-display">
    <div class="product-container">
      <div class="product-image">    
        <img v-bind:src="image">
      </div>
      <div class="product-info">
        <h1>{{ product }}</h1>
        <p v-if="inStock">In Stock</p>
        <p v-else>Out of Stock</p>
        <h2>Composants</h2>
      <ul>
        <li v-for="detail in details" :key="detail">{{detail}}</li>
      </ul>
      <h3>Couleurs disponibles</h3>
      <div class="colors">
        <button class="button" v-for="variant in variants" :key="variant.id" :style="{backgroundColor: variant.color}"></button>
      </div>
      <h3 class="size">Tailles</h3>
      <ul>
        <li v-for="size in sizes" :key="size">{{size}}</li>
      </ul>
      </div>
    </div>
  </div>
</template>