<script setup>
import { ref, reactive } from "vue";
const choose = ref(0);
const persons = reactive([
  { name: "John Due", age: 23, region: "US" },
  { name: "John Due 2", age: 24, region: "UK" },
  { name: "John Due 3", age: 53, region: "BD" },
  { name: "John Due 4", age: 83, region: "IN" },
]);
</script>

<template>
  <div>
    <p class="p-4">Your Score: 10</p>
    <div class="border rounded p-4 gap-10">
      <p>{{ persons }}</p>
      <p class="p-1">Choose Person</p>
      <select v-model="choose">
        <option v-for="(person, index) in persons" :key="index" :value="index">
          {{ person.name }}
        </option>
      </select>
      <span>Name: </span><input type="text" v-model="persons[choose].name" />
      <span>Age: </span><input type="text" v-model="persons[choose].age" />
      <span>Region: </span
      ><input type="text" v-model="persons[choose].region" />
    </div>
  </div>
</template>

<style scoped>
</style>
