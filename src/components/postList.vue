<script setup>

import PostItem from "@/components/postItem.vue";
</script>

<template>
  <div v-if="posts.length > 0">
    <h3>Список</h3>
    <post-item v-for="post in posts" :post="post" :key="post.id"  @remove="$emit('remove', post)"/>
  </div>
  <h2 v-else style="color: red">
      Список постов пуст
  </h2>


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