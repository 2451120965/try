<template>
    <div class="person">
        <h1>Hello, Vue 3!</h1>
        <h2>{{ name }}</h2>
        <h2>{{ num }}</h2>
        <div @click="handleClick">click</div>
        <div @click="changeName">click to changeName</div>
    </div>
</template>

<script setup>
    import { ref } from 'vue'
    let name = ref('Vue 3.0')
    let num = ref(3)

    function handleClick() {
        num.value += 1
    }
    function changeName() {
        name.value = 'Vue 3.2'
    }
</script>

<style scoped>
.person {
    padding: 16px;
    font-family: Arial, sans-serif;
}
</style>