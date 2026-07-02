<script setup>
import Button from "./components/Button.vue";
import Card from "./components/Card.vue";
import Header from "./components/Header.vue";

function turn(isAnswerShown) {
  console.log(isAnswerShown);
}

function changeStatus(approved) {
  console.log(approved);
}
</script>

<template>
  <Header />
  <Card
    :id="1"
    question="Question"
    answer="Answer"
    @turn="turn"
    @change-status="changeStatus"
  />
  <Button>Начать игру</Button>
</template>
