<script setup>
import HeartIcon from "../icons/HeartIcon.vue";
const { score = 0 } = defineProps({ score: Number });
</script>

<template>
  <div class="likes">
    <span>{{ score }}</span> <HeartIcon />
  </div>
</template>

<style scoped>
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