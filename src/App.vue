<template>
  <splash-screen :isLoading="isLoading"/>
  <div class="mainpage-view">
    <div class="scrollable-container">
      <main v-if="!isLoading">
        <home/>
<!--        <SlidingText/>-->
        <about/>
      </main>
    </div>
  </div>
</template>

<script>
import Home from "@/views/Home.vue";
import About from "@/views/About.vue";
import SplashScreen from "@/components/splashScreen.vue";
import SlidingText from "@/views/SlidingText.vue";
import '@/assets/css/scrollbar.css';

export default {
  name: 'App',
  components: {SlidingText, SplashScreen, About, Home},
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
