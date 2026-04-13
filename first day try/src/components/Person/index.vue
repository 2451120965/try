<template>
  <div class="person">
    <h1>Hello, Vue 3!</h1>
    <h2>{{ name }}</h2>
    <h2>{{ num }}</h2>
    <div>{{ price }}</div>
    <div>{{ car.a.b.c }}</div>
    <div @click="handleClick">click</div>
    <div @click="changeName">click to changeName</div>
    <div @click="changePrice">click to changePrice</div>
    <div @click="changeCar">click to changeCar</div>
  </div>
</template>

<script setup>
import { ref, reactive, toRefs } from 'vue'
let name = ref('Vue 3.0')
let num = ref(3)
let car = reactive({
  name: 'baoma',
  price: 30000,
  a: {
    b: {
      c: 1
    }
  }
})

let newObj = {
  name: 'newObj',
  price: 10000,
  a: {
    b: {
      c: 2
    },
    d: 3
  }
}
function changeCar() {
  Object.assign(car, newObj)
  console.log(car);
}

let price = toRefs(car).price
function changePrice() {
  price.value = Math.random() * 100000
  console.log(car.price);
}

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