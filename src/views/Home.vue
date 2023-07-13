<template>
  <nav-bar/>
  <section class="hero-section">
    <div class="content-container" data-aos="fade-up">
      <h1 class="hero-title">(welcome to)</h1>
      <div class="hero-image-container">
        <img src="@/assets/home/CTRL+y-Home.png">
      </div>
      <p class="hero-subtitle">A designathon created by students at the University of Waterloo</p>
      <div class="hero-tv-container">
        <img src="@/assets/home/tvsvg.svg">
      </div>
    </div>
  </section>
</template>

<script>
import NavBar from "@/components/navBar.vue";

export default {
  components: {NavBar}
}
</script>

<style>
.hero-section {
  display: block;
  text-align: center;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 2em 1em;
  text-size-adjust: 100%;
  min-height: 800px;
}

.hero-title {
  color: #09702C;
  font-size: 3.3em;
  font-weight: 500;
  font-style: normal;
  text-align: center;
  line-height: 30px;
  letter-spacing: -3px;
  text-size-adjust: 100%;
  padding-bottom: 1rem;
  padding-top: 3rem;
}

.hero-subtitle {
  color: #09702C;
  font-size: 27px;
  font-weight: 400;
  text-align: center;
  text-size-adjust: 100%;
  display: inline-block; /* Added display property */
  max-width: 30%; /* Set a maximum width for wrapping */
  line-height: 25px;
  letter-spacing: -1.5px;
}

.hero-image-container img {
  padding-top: 1.5rem;
  width: 60%;
  text-size-adjust: 100%;
}

.hero-tv-container img {
  padding-top: 4rem;
  width: 80vw;
  height: auto;
  text-size-adjust: 100%;
  justify-content: center;
  margin-left: 35vw;
}

.content-container {
  text-size-adjust: 100%;
}

template {
  scroll-behavior: smooth;
}

@media (min-width: 768px) {
  .hero-section {
    flex-direction: row;
    justify-content: space-around;
    text-size-adjust: 100%;
  }
  .content-container {
    margin-bottom: 0;
    width: 100%;
    text-size-adjust: 100%;
  }
}
</style>
