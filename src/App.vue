<script setup>
import { ref } from "vue";
import Button from "./components/Button.vue";
import Card from "./components/Card.vue";
import Header from "./components/Header.vue";


function turn(id) {
  cards.value[id-1].state = "opened";
}

function changeStatus(id, status) {
  cards.value[id-1].status = status;
}

const cards = ref([
  {
    id: 1,
    word: "Question",
    translation: "Answer",
    state: "opened",
    status: "pending",
  },
  {
    id: 2,
    word: "Question",
    translation: "Answer",
    state: "closed",
    status: "pending",
  },
  {
    id: 3,
    word: "Question",
    translation: "Answer",
    state: "opened",
    status: "fail",
  },
  {
    id: 4,
    word: "Question",
    translation: "Answer",
    state: "opened",
    status: "success",
  }
]);
</script>

<template>
  <Header />
  <div class="cards">
    <Card
      v-for="card in cards"
      :key="card.id"
      :id="card.id"
      :question="card.word"
      :answer="card.translation"
      :state="card.state"
      :status="card.status"
      @turn="turn"
      @change-status="changeStatus"
    />
  </div>
  <Button>Начать игру</Button>
</template>

<style scoped>
.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 30px;
}
</style>