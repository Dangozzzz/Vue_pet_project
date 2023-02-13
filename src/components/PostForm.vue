<template>
    <form @submit.prevent>
      <h4>Создание поста</h4>
    
    <!-- 2 вариант создания синхронизации с input       @input="title = $event.target.value" -->
    <input 
      v-bind:value="title"
      @input="title = $event.target.value"
      type="text" 
      class="input" 
      placeholder="Название">
     

     <!-- 2 вариант создания синхронизации с input       @input="body = $event.target.value"  (первый находится в script)-->
    <input 
      v-bind:value="body"  
      @input="body = $event.target.value"
      type="text" 
      class="input" 
      placeholder="Описание">
    
    
    <button 
      class="btn" >Создать</button>

    </form>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>
form{
  display: flex;
  flex-direction: column;
  
}
.input{
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}
.btn{
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;
}
</style>