<template>
  <home/>
  <about/>
</template>

<script>
import Home from "@/views/Home.vue";
import About from "@/views/About.vue";
export default {
  name: 'App',
  components: {About, Home}
};
</script>

<style>
</style>
