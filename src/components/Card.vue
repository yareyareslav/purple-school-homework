<script setup>
import ApproveIcon from "../icons/ApproveIcon.vue";
import RejectIcon from "../icons/RejectIcon.vue";

const { id, question, answer, status, state } = defineProps({
  id: Number,
  question: String,
  answer: String,
  status: String,
  state: String,
});
// const state = ref(false);
const emit = defineEmits(["turn", "change-status"]);

function turn() {
  emit("turn", id);
}

function approve() {
  emit("change-status", id, "success");
}
function reject() {
  emit("change-status", id, "fail");
}

console.log(state, status);
</script>

<template>
  <div class="card">
    <div class="card-inner">
      <div class="id">{{ id }}</div>
      <div v-show="state === 'opened'" class="status">
        <ApproveIcon v-if="status === 'success'" />
        <RejectIcon v-else-if="status === 'fail'" />
      </div>
      <div v-if="state === 'closed'" class="question">{{ question }}</div>
      <div v-else class="answer">{{ answer }}</div>
      <div class="btns">
        <button v-if="state === 'closed'" class="btn-turn" @click="turn">
          Перевернуть
        </button>
        <div v-else-if="status === 'pending'" class="btns-status">
          <button class="btn btn-reject" @click="reject">
            <RejectIcon />
          </button>
          <button class="btn-approve" @click="approve"><ApproveIcon /></button>
        </div>
        <div class="btn-turn" v-else>Завершено</div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  font-family: var(--font);

  min-height: 376px;
  width: 100%;
  max-width: 250px;

  display: flex;
  flex-direction: column;

  padding: 28px 19px;
  background-color: var(--color-bg-card);
  box-shadow: 0px 0px 16px 0px #0000001a;
  border-radius: 16px;
}
.card-inner {
  flex: 1;
  position: relative;

  height: 100%;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

  padding: 16px;

  border: 1px solid var(--color-bg-light);
  border-radius: 11px;
}
.id {
  position: absolute;
  top: 0;
  left: 16px;
  transform: translateY(-50%);

  background-color: var(--color-bg-card);
  padding-inline: 4px;
}
.status {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translate(-50%, -50%) scale(2);
}
.question {
  font-size: 18px;
  text-align: center;
}
.answer {
  font-size: 18px;
  text-align: center;
}
.btns {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translate(-50%, 50%);

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  background-color: var(--color-bg-card);
}
.btns-status {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 32px;
  width: 100%;
}
.btn-turn {
  text-transform: uppercase;
  padding-inline: 4px;

  font-weight: 700;
  font-size: 14px;
}
</style>
