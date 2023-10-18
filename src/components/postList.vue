<script setup>

import PostItem from "@/components/postItem.vue";
</script>

<template>
  <div>
    <h3>Список</h3>
    <post-item v-for="post in posts"  :post="post"/>
  </div>



</template>

<script>
import postItem from "@/components/postItem.vue";
  export default {
    props: {
      posts: {
        type: Array,
        required: true
      }
    }
  }
</script>

<style scoped>

</style>