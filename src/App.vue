<script setup>
import { ref } from "vue";
import Button from "./components/Button.vue";
import Card from "./components/Card.vue";
import Header from "./components/Header.vue";

function turn(isAnswerShown) {
  console.log(isAnswerShown);
}

function changeStatus(approved) {
  console.log(approved);
}

const card = ref({
  id: 1,
  word: "Question",
  translation: "Answer",
  state: "closed",
  status: "success",
});
</script>

<template>
  <Header />
  <Card
    :id="card.id"
    :question="card.word"
    :answer="card.translation"
    @turn="turn"
    @change-status="changeStatus"
  />
  <Button>Начать игру</Button>
</template>
