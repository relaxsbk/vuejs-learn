<template>
  <div class="formPost">
    <form @submit.prevent >
      <h4>Создание поста</h4>
      <my-input v-model="post.title" type="text" placeholder="Название"/><br>
      <my-input v-model="post.description"  type="text" placeholder="Описание"/><br>
      <my-button @click="createPost" class="btn" style="margin-top: 15px">Создать</my-button>
    </form>
  </div>
</template>

<script>




export default {

  data() {
    return {
      post: {
        title: '',
        description: '',
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit('create', this.post)
      this.post = {
        title: '',
        description: '',
      }
    }
  }
}
</script>

<style scoped>
.formPost {
  display: flex;
  flex-direction: column;
}




</style>