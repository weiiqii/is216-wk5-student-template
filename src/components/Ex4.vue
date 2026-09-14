<script setup>
import { ref } from 'vue'
const items = ref(['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'])

// TODO: Add Code Here
const text = ref('')
const removeItem = (index) => {
  items.value.splice(index, 1)
}
const addItem = () => {
  items.value.push(text.value)
  text.value = ''
}

</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
    <ul>
        <li v-for="(item, index) in items" :key="item">
            {{ item }}
            <button @click="removeItem(index)">Delete!</button>
            <!-- <button @click="items.splice(index)">Delete!</button> -->
        </li>
    </ul>
    <br>
    <input v-model="text" @keyup.enter="addItem"/>
    <button @click="addItem">Add</button>
</template>
