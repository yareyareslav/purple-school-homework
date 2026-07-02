<script setup>
import HeartIcon from "../icons/HeartIcon.vue";
import Score from "./Score.vue";
</script>

<template>
  <header class="header">
    <h1 class="title">Запомни слово</h1>
    <Score score="100" />
  </header>
</template>

<style scoped>
.header {
  width: calc(100%-74px);
  max-width: 1440px;

  margin-inline: auto;
  padding: 37px;

  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 0 0 30px 0;
  font-size: 16px;
}
.title {
  text-transform: uppercase;
  font-family: var(--font);
  font-weight: 700;
}
.likes {
  padding: 12px 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;

  font-family: var(--font);
  font-weight: 700;
  color: var(--color-bg);

  background-color: var(--color-bg-light);
  box-shadow: 0px 0px 4px 0px #00000026;
  border-radius: 36px;
}
</style>
