<template>
  <splash-screen :isLoading="isLoading"/>
  <main v-if="!isLoading">
    <home/>
    <about/>
  </main>
</template>

<script>
import Home from "@/views/Home.vue";
import About from "@/views/About.vue";
import SplashScreen from "@/components/splashScreen.vue";

export default {
  name: 'App',
  components: {SplashScreen, About, Home},
  data() {
    return { isLoading: true };
  },
  mounted() {
    setTimeout(() => {
      this.isLoading = false;
    }, 1800);
  }
};
</script>
<style>
</style>
