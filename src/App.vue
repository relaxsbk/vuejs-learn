<script setup>

import MyDialog from "@/components/MyDialog.vue";
import MyButton from "@/components/UI/MyButton.vue";
</script>

<template>
<div class="app">
  <h1>Страница с постами</h1>
  <my-dialog :show="dialogVisible">
    <post-form @create="createPost"/>
  </my-dialog>
  <my-button @click="showDialog">Создать пост</my-button>

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
      dialogVisible: false,
    }
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
      this.dialogVisible = false;
    },
    removePost(post) {
      this.posts = this.posts.filter(p => p.id !== post.id)
    },
    showDialog() {
      this.dialogVisible = true;
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