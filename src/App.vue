<script setup>

</script>

<template>
<div class="app">
    <post-form @create="createPost"/>
    <post-list :posts="posts" @remove="removePost" />


</div>
</template>

<script>
import postForm from "@/components/postForm.vue";
import postList from "@/components/postList.vue";

export default {
  components: {
    postList, postForm,
  },

  data() {
    return {
      posts: [
        {id: 1, title: 'JS', description: 'Описание лоол'},
        {id: 2, title: 'JS 2', description: 'Описание лоол 2'},
        {id: 3, title: 'JS 3', description: 'Описание лоол 3'},
        {id: 4, title: 'JS 4', description: 'Описание лоол 4'},
      ],
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
    removePost(post) {
      this.posts = this.posts.filter(p => p.id !== post.id)
    }

  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}




</style>