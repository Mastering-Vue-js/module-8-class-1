<script setup>
import { ref, reactive } from "vue";
const input = ref("Test");
const input2 = ref("Test2");
const input3 = ref(2);
const check = ref([]);
const radio = ref('');
const select = ref('');
// const takeInput = (e) => {
//   input.value = e.target.value;
// };
</script>

<template>
  <div>
    <p class="p-4">Output: {{ input }}</p>
    <!-- <span>Input: </span
    ><input type="text" :value="input" @input="takeInput($event)" /> -->
    <span class="p-4">Input: </span><input type="text" v-model="input" />
    <p class="p-4">Check: {{ check }}</p>
    <span class="p-4">Input: </span>
    <label for=""><input type="checkbox" value="class" v-model="check" />Class</label>
    <label for=""><input type="checkbox" value="record" v-model="check" />Record</label>
    <p class="p-4">Radio: {{ radio }}</p>
    <span class="p-4">Input: </span>
    <label for=""><input type="radio" value="class" v-model="radio" />Class</label>
    <label for=""><input type="radio" value="record" v-model="radio" />Record</label>
    <p class="p-4">Select: {{ select }}</p>
    <select name="" id="" v-model="select">
        <option value="1">1</option>
        <option value="2">2</option>
        <option value="3">3</option>
        <option value="4">4</option>
    </select>
    <p class="p-4">Output: {{ input2 }}</p>
    <span class="p-4">Input: </span><input type="text" v-model.trim="input2" />
    <p class="p-4">Output: {{ input3 }}</p>
    <span class="p-4">Input: </span><input type="text" v-model.number="input3" />
  </div>
</template>

<style scoped>
</style>
