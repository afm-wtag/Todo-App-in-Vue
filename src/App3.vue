<script setup>
import { ref, onMounted } from "vue";
const name = ref("Afnan Mumu");
const status = ref("active");
const tasks = ref(["Task One", "Task Two"]);
const newTask = ref("");
const toggleStatus = () => {
  if (status.value === "active") status.value = "pending";
  else if (status.value === "pending") status.value = "inactive";
  else status.value = "active";
};
const addTask = () => {
  if (newTask.value.trim() != "") {
    tasks.value.push(newTask.value.trim());
    newTask.value = "";
  }
};
const deleteTask = (index) => {
  tasks.value.splice(index, 1);
};
onMounted(async () => {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/todos');
    const data = await response.json();
    tasks.value = data.map((task) => task.title);
  } catch (error) {
    console.log('Error Fetching Tasks')
  }
});
</script>
<template>
  <h1>{{ name }}</h1>
  <p>User is {{ status }}</p>
  <form @submit.prevent="addTask">
    <span>Enter a new task</span>
    <input type="text" id="newTask" v-model="newTask" />
    <button type="submit">Submit</button>
  </form>
  <ul>
    <li v-for="(task, index) in tasks" :key="task">
      <span>{{ task }}</span
      ><button @click="deleteTask(index)">*</button>
    </li>
  </ul>
  <button @click="toggleStatus">Status</button>
</template>
