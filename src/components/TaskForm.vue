<template>
  <form @submit.prevent="formSubmitted">
    <label>
      New Task
      <input v-model="newTask" type="text" name="newTask" />
    </label>
    <div class="button-container">
      <button>Add</button>
    </div>
  </form>
</template>

<script setup lang="ts">
import { ref } from "vue";

const emit = defineEmits<{
  addTask: [newTask: string];
}>();

const newTask = ref("");

const formSubmitted = () => {
  emit("addTask", newTask.value);
  newTask.value = "";
};
</script>

<style scoped>
.button-container {
  display: flex;
  justify-content: end;
}
</style>
