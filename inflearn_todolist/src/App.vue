<template>
  <div id="app">
    <TodoHeader/>
    <TodoInput/>
    <TodoList/>
    <TodoFooter/>
  </div>
</template>

<script>
import TodoHeader from "./components/TodoHeader.vue";
import TodoFooter from './components/TodoFooter.vue';
import TodoList from './components/TodoList.vue';
import TodoInput from './components/TodoInput.vue';

  export default {
    components : {
      TodoFooter,
      TodoHeader,
      TodoInput,
      TodoList
    }    
  }
</script>

<style>
body{
  text-align: center;
  background-color: aliceblue;
}

input{
  border-style: groove;
  width: 200px;
}

button{
  border-style: groove;
}
.shadow{
  box-shadow: 5px 10px 10px rgba(0,0,0,0.05);
}
</style>