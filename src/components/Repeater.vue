<script setup>
import { ref, reactive } from "vue";
const students = reactive([
  { name: "Rohim", gender: "Male" }
]);
const addNewStudent = () => {
  students.push({ name: "", gender: "" });
  // students.unshift({ name: "", gender: "" });
};
</script>

<template>
  <div>
    <p class="p-4">{{ students }}</p>
    <div class="border rounded p-4 gap-10">
      <p class="p-1">Students</p>
      <div class="block m-2" v-for="(student, index) in students" :key="index">
        <label class="p-2">Name: </label
        ><input type="text" v-model="student.name" />
        <label class="p-2"
          ><input
            class="pr-2"
            type="radio"
            value="Male"
            v-model="student.gender"
          /><span class="pl-2">Male</span></label
        >
        <label class="p-2"
          ><input
            class="pr-2"
            type="radio"
            value="Female"
            v-model="student.gender"
          /><span class="pl-2">Female</span></label
        >
      </div>
      <button class="block border rounded p-4 m-4" @click="addNewStudent()">
        Add New Student
      </button>
    </div>
  </div>
</template>

<style scoped>
</style>
