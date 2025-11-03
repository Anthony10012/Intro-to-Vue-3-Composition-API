<script setup>
import { ref } from 'vue'
import socksGreenImage from './assets/images/socks_green.jpeg'

const product = ref('Socks')
const image = ref(socksGreenImage)
const inventory = 11
const onSale = false
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
        <p v-if="inventory > 10">En stock</p>
        <p v-else-if="inventory >=1">Faible stock</p>
        <p v-else>En rupture de stock</p>
        <p v-if="onSale">En solde</p>
      </div>
    </div>
  </div>
</template>