<script setup>
import {ref} from 'vue'
const review = ref({
  name: '',
  content: '',
  rating: null,
  recommand: ''
})

const emit = defineEmits(['review-submitted'])

function onSubmit(){
  if (!review.value.name || !review.value.content || review.value.rating === null || !review.value.recommand){
    alert('Un des champs est vide. Veuillez indiquer votre nom, votre avis et une note ')
    return
  }
  const productReview = {
  name: review.value.name,
  review: review.value.content,
  rating: review.value.rating,
  recommand: review.value.recommand
}

// Emit au parent App.vue
emit('review-submitted',productReview)

// Reset
review.value.name = ''
review.value.content = ''
review.value.rating = null
review.value.recommand = ''
}


</script>

<template>
  <form class="review-form" @submit.prevent="onSubmit" >
    <h3>Leave a review</h3>
    <label for="name">Name:</label>
    <input id="name" v-model="review.name">

    <label for="review">Review:</label>      
    <textarea id="review" v-model="review.content"></textarea>

    <label for="rating">Rating:</label>
    <select id="rating" v-model.number="review.rating">
      <option>5</option>
      <option>4</option>
      <option>3</option>
      <option>2</option>
      <option>1</option>
    </select>

    <label for="recommand">Recommanderiez-vous ce produit ?</label>
    <select id="recommand" v-model="review.recommand">
      <option value="" disabled selected>Choisir...</option>
      <option value="Yes">Yes</option>
      <option value="No">No</option>
    </select>

    <input class="button" type="submit" value="Submit">
  </form>
</template>

