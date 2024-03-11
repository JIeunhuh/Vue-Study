<!-- vue - cli활용해서 app-> appheader로 props넘기고 emit으로 데이터 받아서 변경한 후 다시 props로 전달하기  -->
<template>
    <app-header/>
    <div>
        {{message}}
    </div>
    <!-- v-on:click -> @click 으로 가능 -->
    <button @click="showAlert">click</button>
</template>

<script>
// component를 import(가져옴)
import AppHeader from './components/AppHeader.vue';

export default {
	// component 등록
    components :{
        'app-header' : AppHeader
    },
    data() {
        return {
            message : 'value',
        }
    },
    methods: {
        showAlert() {
            alert('hello')
        }
    },
}
</script>

<style scoped>
</style>./AppHeader.vue