<template>
  <splash-screen v-if="isLoading" :isLoading="isLoading" />
  <main v-if="!isLoading">
    <div ref="componentsBeforeIntro">
      <home />
    </div>
    <pre-introduction :reached-intro="reachedIntro"/>
    <introduction :reachedIntro="reachedIntro" />
    <description/>
    <sponsors/>
    <faq/>
    <OurTeam/>
  </main>
</template>

<script>
import Home from "@/views/Home.vue";
import About from "@/views/About.vue";
import Introduction from "@/views/Introduction.vue";
import Description from "@/views/Description.vue";
import SplashScreen from "@/components/splashScreen.vue";
import SlidingText from "@/views/SlidingText.vue";
import PreIntroduction from "@/views/preIntroduction.vue";
import Sponsors from "./views/Sponsors.vue";
import Faq from "./views/Faq.vue"
import OurTeam from "@/views/OurTeam.vue";
import '@/assets/css/scrollbar.css';

export default { 
  name: 'App',
  components: { PreIntroduction, SlidingText, SplashScreen, About, Home, Introduction, Description, Sponsors, Faq, OurTeam },
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
