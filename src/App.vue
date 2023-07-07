<template>
  <splash-screen :isLoading="isLoading"/>
  <main v-if="!isLoading">
    <SlidingText/>
    <home/>
    <about/>
    <introduction/>
  </main>
</template>

<script>
import Home from "@/views/Home.vue";
import About from "@/views/About.vue";
import Introduction from "@/views/Introduction.vue";
import SplashScreen from "@/components/splashScreen.vue";
import SlidingText from "@/views/SlidingText.vue";

export default {
  name: 'App',
  components: {SlidingText, SplashScreen, About, Home, Introduction},
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
