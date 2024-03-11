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
</style>