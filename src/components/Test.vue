<script setup>
const objectOfAttrs = {
  id: "container",
  class: "wrapper",
  style: "background-color:green",
};
</script>
<template>
  <div v-bind="objectOfAttrs">hello</div>
</template>
