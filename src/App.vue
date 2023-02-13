<template>
  <!-- <div> -->

  <!-- Динамическое добавление постов -->
  <div class="app">



 
<!-- КОРОТКАЯ ЗАПИСЬ :posts  ПОЛНАЯ ЗАПИСЬ v-bind:posts -->
     <post-form/>
     <post-list :posts="posts"/>




    <!-- Тут была работа с массивами 22:41 -->
    <!-- <div> <strong> Название:</strong> Пост о JavaScript</div>
    <div> <strong> Описание:</strong> JavaScript</div> -->
    <!-- Можно дублировать так или Создать массив постов -->
    <!-- </div>
    <div class="post">
    <div> <strong> Название:</strong> Пост о JavaScript</div>
    <div> <strong> Описание:</strong> JavaScript</div>
    </div>
    <div class="post">
    <div> <strong> Название:</strong> Пост о JavaScript</div>
    <div> <strong> Описание:</strong> JavaScript</div>
    </div> -->





    <!-- <div> -->
    <!-- <button @click="addLike">Likes</button>
    <button @click="addDislike">Dislike</button>
    </div>
    <div>Кол-во лайков <strong>{{ likes }}</strong> </div>
    <div>Кол-во дилайков <strong>{{ dislikes }}</strong> </div> -->


  </div>
</template>


<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";

export default {
  
  components: {
    PostList, PostForm
  },

  data() {
    return {
      posts: [
        { id: 1, title: " javaScript", body: "Описание поста" },
        { id: 2, title: " javaScript", body: "Описание поста 2" },
        { id: 3, title: " javaScript", body: "Описание поста 3" },
      ],
      title: '',
      body: '',
    };
  },


  methods: {
    // Двустороннее связывание 
createPosts(   ){
  const newPost = {
    id: Date.now(),
    title: this.title,
    body: this.body,
  }
  this.posts.push(newPost);
  this.title = '';
  this.body = '';

},
// Синхронизаия модели с input
// inputTitle(event){
//   this.title = event.target.value;
// }



    // Тут был метод создания лайков 10:15
    // addLike(){
    //   this.likes += 1;
    // },
    // addDislike(){
    //   this.dislikes += 1;
    // },
  },
};
</script>


<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app{
  padding: 20px;
}
</style>
