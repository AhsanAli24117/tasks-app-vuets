<script setup lang="ts">
import { ref } from "vue";
import TaskForm from "./components/TaskForm.vue";

const message = ref("Tasks App");

const addTask = (newTask: string) => {
  console.log(newTask);
};
</script>

<template>
  <main>
    <h1>{{ message }}</h1>
    <TaskForm @add-task="addTask" />
  </main>
</template>

<style scoped>
main {
  width: 800px;
  margin: 1rem auto;
}
</style>
