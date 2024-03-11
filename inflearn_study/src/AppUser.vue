<!-- v-model로 입력받는 id, pw값 데이터 속성에 연결해 나타내기 -->
<template>
    <form action="" v-on:submit.prevent="submitForm">
      <div>
        <label for=""></label>
        <input type="text" v-model="username">
      </div>
      <div>
        <label for=""></label>
        <input type="password" v-model="password">
      </div>
  
      <button type="submit">Sign in !</button>
    </form>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        username: '',
        password: ''
      }
    },
    methods: {
      submitForm() {
        // vue에선 v-on 디렉티브에서 .prevent로 이벤트 제어를 할 수 있다 !
        // page 재렌더링하지 않음
        // e.preventDefault();
        const data = {
          username: this.username,
          password: this.password
        }
        // axios.method 방식('api', 보낼 인자값),then(응답처리)
        axios.post('https://jsonplaceholder.typicode.com/users/', data)
          .then(response => {
            console.log(response);
          });
        console.log('제출됨')
      }
    },
  }
  </script>
  
  <style scoped></style>