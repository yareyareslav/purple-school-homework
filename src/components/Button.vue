<script setup></script>

<template>
    <button class="btn"><slot /></button>
</template>

<style scoped>
.btn {
  max-width: 335px;
  width: 100%;
  padding: 16px 10px;

  font-family: var(--font);
  font-size: 24px;
  background-color: var(--color-bg);
  color: white;

  border: none;
  border-radius: 100px;
}
</style>
