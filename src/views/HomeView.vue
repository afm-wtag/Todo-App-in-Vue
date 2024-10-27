<script setup>
import Hero from "@/components/Hero.vue";
import HomeCards from "@/components/HomeCards.vue";
import JobListings from "@/components/JobListings.vue";
</script>
<template>
    <Hero title="Unlock Your Future" subtitle="Discover Opportunities Tailored to Your Skills and Ambitions." />
  <HomeCards />
  <JobListings :limit="3" :showButton="true"/>
</template>