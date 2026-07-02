<script setup>
import Button from './components/Button.vue'
import Card from './components/Card.vue';
import Header from './components/Header.vue';
</script>

<template>
  <Header />
  <Card :id="1" question="Question" answer="Answer" />
  <Button>Начать игру</Button>
</template>
