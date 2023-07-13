<template>
  <splash-screen :isLoading="isLoading" />
  <main v-if="!isLoading">
    <div ref="componentsBeforeIntro">
      <SlidingText />
      <home />
      <about />
    </div>
    <introduction :reachedIntro="reachedIntro" />
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
  components: { SlidingText, SplashScreen, About, Home, Introduction },
  methods: {
    scroll() {
      window.onscroll = () => {
        if (!this.reachedIntro) { // so that it doesn't keep loading the animation
          const heightOfPrevElements = this.$refs.componentsBeforeIntro.offsetHeight - 50;
          this.reachedIntro = Math.max(window.scrollY, document.documentElement.scrollTop, document.body.scrollTop) + window.innerHeight >= heightOfPrevElements;
        }
      }

    }
  },
  data() {
    return {
      isLoading: true,
      reachedIntro: false,
      aboutHeight: 0
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
<style></style>
