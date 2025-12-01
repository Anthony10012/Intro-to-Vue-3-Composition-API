<script setup>
const props = defineProps({
    reviews:{
        type: Array,
        required: true
    }
})
</script>

<template>
 <div class="review-container" v-if="reviews.length">
    <h3>Review :</h3>
    <ul>
        <li v-for="(rev, index) in reviews" :key="index">
            <p><strong> Name:</strong>  {{rev.name}}</p>
            <p><strong> Rating :</strong>  {{rev.rating}}/5</p>
            <p><strong> Content:</strong> {{rev.review}}</p>
            <p><strong> Recommand:</strong> {{rev.recommand}}</p>
            

        </li>
    </ul>
 </div>

</template>

