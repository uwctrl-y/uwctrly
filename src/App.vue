<template>
  <splash-screen v-if="isLoading" :isLoading="isLoading" />
    <main v-if="!isLoading">
    <div ref="componentsBeforeIntro">
      <nav-bar/>
      <home id="home"/>
    </div>
    <pre-introduction :reached-intro="reachedIntro" id="pre-introduction"/>
    <introduction :reachedIntro="reachedIntro" id="introduction"/>
    <WhatsGoingDown id="whats-going-down"/>
    <sponsors id="sponsors"/>
    <faq id="faq"/>
    <OurTeam id="our-team"/>
    <registration id="registration"/>
  </main>
</template>

<script>
import NavBar from "./components/navBar.vue"
import Home from "@/views/Home.vue";
import About from "@/views/About.vue";
import Introduction from "@/views/Introduction.vue";
import WhatsGoingDown from "./views/WhatsGoingDown.vue";
import Registration from "@/views/Registration.vue"
import SplashScreen from "@/components/splashScreen.vue";
import SlidingText from "@/views/SlidingText.vue";
import PreIntroduction from "@/views/preIntroduction.vue";
import Sponsors from "./views/Sponsors.vue";
import Faq from "./views/Faq.vue"
import OurTeam from "@/views/OurTeam.vue";
import '@/assets/css/scrollbar.css';

export default { 
  name: 'App',
  components: { NavBar, PreIntroduction, SlidingText, SplashScreen, About, Home, Introduction, WhatsGoingDown, Sponsors, Faq, OurTeam, Registration },
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
