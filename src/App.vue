<template>
  <splash-screen :isLoading="isLoading"/>
  <main v-if="!isLoading">
    <SlidingText/>
    <home/>
    <about/>
    <introduction :reachedIntro="reachedIntro"/>
  </main>
</template>

<script>
import Home from "@/views/Home.vue";
import About from "@/views/About.vue";
import Introduction from "@/views/Introduction.vue";
import SplashScreen from "@/components/splashScreen.vue";
import SlidingText from "@/views/SlidingText.vue";
import { ref, onMounted } from 'vue'

export default {
  name: 'App',
  components: { SlidingText, SplashScreen, About, Home, Introduction },
  methods: {
    scroll() {
      window.onscroll = () => {
        if (!this.reachedIntro) { // so that it doesn't keep loading the animation
          const heightOfPrevElements = 1200; // replace this with an actual calculation (sum of heights of previous elements)
          this.reachedIntro = Math.max(window.scrollY, document.documentElement.scrollTop, document.body.scrollTop) + window.innerHeight >= heightOfPrevElements;
      }
      }
    }
  },
  data() {
    return { 
      isLoading: true,
      reachedIntro: false,
    };
  },
  mounted() {
    this.scroll();
    setTimeout(() => {
      this.isLoading = false;
    }, 1800);
  }
};
</script>
<style>
</style>
