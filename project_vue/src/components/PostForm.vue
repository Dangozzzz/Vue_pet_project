<template>
  <form @submit.prevent>
    <h4>Создание поста</h4>

    <!-- =============================Start============================= -->
    <!-- 2 вариант создания синхронизации с input       @input="title = $event.target.value" 
    -->

    <!-- <input 
      v-bind:value="post.title"
      @input="post.title = $event.target.value"
      type="text" 
      class="input" 
      placeholder="Название">
      -->
    <!-- 2 вариант создания синхронизации с input       @input="body = $event.target.value"  (первый находится в script)-->
    <!-- <input 
      v-bind:value="post.body"  
      @input="post.body = $event.target.value"
      type="text" 
      class="input" 
      placeholder="Описание"> -->
    <!-- ================================End========================= -->

    <!-- Дусторонее связывание с использованием дерективы v-model="post.body "
      ===================Убрали========================v-bind:value="post.title"
      ===================Убрали========@input="post.title = $event.target.value" -->
    <input
      v-model="post.title"
      type="text"
      class="input"
      placeholder="Название"
    />

    <input
      v-model="post.body"
      type="text"
      class="input"
      placeholder="Описание"
    />

    <!-- Повесили слуштель обытия создания на кнопку @click ="/(создаем функцию)\ createPost" далее добавили поле methods
     в script компонент -->
    <button class="btn" @click="createPost">Создать</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit('create', this.post)
      this.post = {
        title: "",
        body: "",
    }
  }
  
}
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}
.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}
.btn {
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}
</style>
