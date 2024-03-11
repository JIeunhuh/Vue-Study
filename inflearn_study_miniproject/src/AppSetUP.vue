<!-- Composition API -->
<template>
  <div>
    <form action="" method="post" @submit.prevent=submitForm>
      <div>
        <label for="username">ID:</label>
        <input type="text" v-model=username id="username">
      </div>
      <div>
        <label for="password">PW:</label>
        <input type="password" v-model=password id="password">
      </div>

      <button type="submit" >Log in!</button>
    </form>
  </div>
</template>

<script>
import { ref } from 'vue';
import axios from 'axios';

export default {
  // data() 대신 ref() 이용
  setup() {
    const username = ref('');
    const password = ref('');

    const submitForm = () => {
      const data = {
        username: username.value,
        password: password.value
      }
      // axios.method 방식('api', 보낼 인자값),then(응답처리)
      axios.post('https://jsonplaceholder.typicode.com/users/', data)
        .then(response => {
          console.log(response);
        });
      console.log('제출됨')
    }
    // setup()에서 리턴된 값들은 모두 methods에서 접근가능하다
    return{
      submitForm, username, password
    }
  },

  methods : {
    userInfo() {
      this.password;
    }
  }
}
</script>

<style lang="scss" scoped></style>