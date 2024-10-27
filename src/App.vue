<script setup>
import Navbar from "./components/Navbar.vue";
import { RouterView } from "vue-router";
// App component is set up here - 1st step
console.log('App component is setup.');
</script>
<template>
  <Navbar />
  <RouterView />
</template>
