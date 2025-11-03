<script setup>
import socksImage from "./assets/images/socks_green.jpeg"

const product = "Socks"
const image = socksImage
const description = "Voici une chaussette "
const url = "https://www.cpnv.ch"
const inStock = true
</script>

<template>
  <div class="product-display">
    <div class="product-container">
      <div class="product-info">
        <h1>{{product}}</h1>
        <p>{{description}}</p>
        <a :href="url" >Visiter le site du CPNV</a>
        <div class="product-image">
          <img :src="image" alt="Image des chaussettes"/>
        </div>
        <p v-show="inStock">En stock</p>
        <p v-show="!inStock">En rupture de stock</p>
      </div>
    </div>
  </div>
</template>

