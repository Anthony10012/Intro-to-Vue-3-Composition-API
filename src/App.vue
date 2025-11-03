<script setup>
import socksImage from "./assets/images/socks_green.jpeg"

const product = "Socks"
const image = socksImage
const description = "Voici une chaussette "
const url = "https://www.cpnv.ch" 
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
      </div>
    </div>
  </div>
</template>

