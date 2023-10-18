<template>
  <div class="formPost">
    <form @submit.prevent >
      <h4>Создание поста</h4>
      <input v-model="post.title" class="input" type="text" placeholder="Название"><br>
      <input v-model="post.description" class="input" type="text" placeholder="Описание"><br>
      <button @click="createPost" class="btn">Создать</button>
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

.input {
  width: 50%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

.btn {
  margin-top: 15px;
  align-self: center;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}
</style>