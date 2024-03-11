<!-- composition API -->
<template>
    <div class="inputBox shadow">
        <input type="text" v-model=inputTxt id="list">
        <!-- <button @click=addItem>add</button> -->
        <span class="addContainer" @click=addItem>
            <i class="fa-solid fa-plus addBtn"></i>
        </span>
    </div>
</template>

<!-- composition API -->
<!-- <script>
import { ref } from "vue";
export default {
    setup () {
    const inputTxt = ref('');
    
        return {inputTxt};
    }
}
</script> -->
<!-- Option API -->
<script>
export default {
    data() {
        return {
            inputTxt: ''
        }
    },
    methods: {
        addItem() {
            // console.log(this.inputTxt);
            // localStorage.setItem(key, value) -> argument 2
            localStorage.setItem("todoList", this.inputTxt);
            this.clearInput()
        },
        clearInput(){
            this.inputTxt=';'
        }
    }
}
</script>
<!-- module.css랑 비슷한 거 같다 -->
<style scoped>
input:focus {
  outline: none;
}
.inputBox {
  background: white;
  height: 50px;
  line-height: 50px;
  border-radius: 5px;
}
.inputBox input {
  border-style: none;
  font-size: 0.9rem;
}
.addContainer {
  float: right;
  background: linear-gradient(to right, #6478FB, #8763FB);
  display: block;
  width: 3rem;
  border-radius: 0 5px 5px 0;
}
.addBtn {
  color: white;
  vertical-align: middle;
}</style>