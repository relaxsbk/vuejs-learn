<script setup>

</script>

<template>
<div class="app">
  <div>
    <form >
      <h4>Создание поста</h4>
      <input class="input" type="text" placeholder="Название"><br>
      <input class="input" type="text" placeholder="Описание"><br>
      <button class="btn">Создать</button>
    </form>
  </div>
  <div class="post" v-for="post in posts">
    <div> <strong>Название:</strong> {{post.title}} </div>
    <div> <strong>Описание:</strong> {{post.description}} </div>

  </div>

</div>
</template>

<script>
export default {
  data() {
    return {
      posts: [
        {id: 1, title: 'JS', description: 'Описание лоол'},
        {id: 2, title: 'JS 2', description: 'Описание лоол 2'},
        {id: 3, title: 'JS 3', description: 'Описание лоол 3'},
        {id: 4, title: 'JS 4', description: 'Описание лоол 4'},
      ]
    }
  },
  methods: {

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

.post {
  padding: 15px;
  border: 2px solid teal;
  margin-top: 15px;
}

form {
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