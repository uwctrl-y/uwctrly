<template>
  <div class="nav-bar">
    <nav class="nav-bar">
    <img class="logo" src="@/assets/home/CTRL+y-Nav.png" alt="Logo" @click="scrollToSection('home')">
    <ul class="navbar-list">
      <li class="navbar-item" @click="scrollToSection('pre-introduction')">about</li>
      <li class="navbar-item" @click="scrollToSection('sponsors')">sponsors</li>
      <!-- <li class="navbar-item" @click="scrollToSection('pre-introduction')">judges</li> -->
      <li class="navbar-item" @click="scrollToSection('faq')">faq</li>
      <li class="navbar-item" @click="scrollToSection('our-team')">team</li>
      <li class="navbar-item" @click="scrollToSection('registration')">registration</li>
    </ul>
    <div class="navbar-item">
      <div>
        interested?
        <br>
        <a style="color:inherit" href="mailto:ctrlplusy2023@gmail.com">Contact Us</a>
      </div>
    </div>
  </nav>
  </div>
</template>

<script>
export default {
  methods: {
    scrollToSection(sectionId) {
      const section = document.getElementById(sectionId);
      if (section) {
        section.scrollIntoView({ behavior: 'smooth'});
      }
    },
  },
};
</script>

<style scoped>
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

@media (max-width: 1028px) {
  .nav-bar {
    display: none;
  }
}
</style>

