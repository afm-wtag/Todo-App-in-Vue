<script>
export default {
  data() {
    return {
      name: "mumu",
      status: "active",
      tasks: ["Task One", "Task Two"],
      link: "https://www.google.com/",
    };
  },
  methods: {
    toggleStatus() {
      if (this.status === "active") this.status = "pending";
      else if (this.status === "pending") this.status = "inactive";
      else this.status = "active";
    },
  },
};
</script>
<template>
  <h1>{{ name }}</h1>
  <p>User is {{ status }}</p>
  <ul>
    <li v-for="task in tasks">{{ task }}</li>
  </ul>
  <a :href="link">Click me</a>
  <button @click="toggleStatus">Status</button>
</template>
