<template>
  <nav class="nav-bar">
    <img class="logo" src="@/assets/home/CTRL+y-Nav.png" alt="Logo">
    <div class="navbar-list">
      <a class="navbar-item" href="#/about" @click="scrollToSection($event, 'about')">about</a>
      <a class="navbar-item" href="#/sponsors">sponsors</a>
      <a class="navbar-item" href="#/judges">judges</a>
      <a class="navbar-item" href="#/faq">faq</a>
      <a class="navbar-item" href="#/ourTeam">team</a>
    </div>
    <div class="navbar-item">
      <div>
        interested?
        <br>
        <span>Contact Us</span>
      </div>
    </div>
  </nav>
</template>

<script setup>
import {ref} from 'vue'
import About from "@/views/About.vue";
import Sponsors from "@/views/Sponsors.vue";
import faq from "@/views/Faq.vue";
import ourTeam from "@/views/OurTeam.vue";
import Judges from "@/views/Judges.vue";

const routes = {
    '/about': About,
    '/sponsors': Sponsors,
    '/judges': Judges,
    '/faq': faq,
    '/ourTeam': ourTeam
}

const scrollToSection = (event, sectionId) => {
    event.preventDefault();
    const targetSection = document.getElementById(sectionId);
    if (targetSection) {
        targetSection.scrollIntoView({
            behavior: 'smooth',
            block: 'start',
        });
    }
    console.log("poop")
}

const currentPath = ref(window.location.hash)

window.addEventListener('hashchange', () => {
    currentPath.value = window.location.hash
})
</script>

<style>
.nav-bar {
  padding-top: 15px;
  display: flex;
  justify-content: space-between;
  align-items: center; /* Add this line to vertically align items */
  width: 100vw;
}

.navbar-list {
  display: flex;
  list-style-type: none;
  justify-content: center;
}

.navbar-item {
  margin: 0 50px;
  font-size: 14px;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
  color: #09702C;
  text-decoration: underline;
}


.logo {
  width: 100px; /* Adjust the width as needed */
  height: auto;
  margin-left: 2rem;
}

</style>