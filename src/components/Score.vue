<script setup>
import HeartIcon from "../icons/HeartIcon.vue";
const { score = 0 } = defineProps({ score: Number });
</script>

<template>
  <div class="likes">
    <span>{{ score }}</span> <HeartIcon />
  </div>
</template>
