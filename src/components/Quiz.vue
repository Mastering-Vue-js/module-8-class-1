<script setup>
import { ref, reactive } from "vue";
const score = ref(0);
const questions = reactive([
  //   { desc: "Is number one is right?", answer: "yes", options: [{value: 'yes', label: 'Yes'}, 'no', 'middle', 'no-comment'] },
  { desc: "Is number one is right?", answer: "yes" },
  { desc: "Is number two is right?", answer: "no" },
  { desc: "Is number three is right?", answer: "yes" },
  { desc: "Is number four is right?", answer: "no" },
  { desc: "Is number five is right?", answer: "yes" },
]);

const calculateScore = () => {
  score.value = 0;
  questions.forEach((question) => {
    if (question.answer == question.input) {
      score.value = score.value + 5;
    }
  });
};
</script>

<template>
  <div>
    <p class="p-4">Your Score: {{ score }}</p>
    <div
      v-for="(question, index) in questions"
      :key="index"
      class="border rounded p-4 gap-10"
    >
      <p class="p-1">{{ question.desc }}</p>
      <label class="p-2"
        ><input
          class="pr-2"
          type="radio"
          @change="calculateScore()"
          value="yes"
          v-model="question.input"
        /><span class="pl-2">Yes</span></label
      >
      <label class="p-2"
        ><input
          class="pr-2"
          type="radio"
          @change="calculateScore()"
          value="no"
          v-model="question.input"
        /><span class="pl-2">No</span></label
      >
    </div>
  </div>
</template>

<style scoped>
</style>
