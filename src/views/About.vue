<template>
  <section class="about-section">
    <div class="content-container" data-aos="fade-up">
      <h1 class="about-title">About CTRL + Y</h1>
      <p class="about-description">
        CTRL + y is a designathon with the focus of designing innovative solutions for the rapidly evolving future of tech. We’re looking for like-minded people who are invested in our mission, and share similar passions for this project.
      </p>
      <div class="cta-button-container">
        <a
            class="cta-button"
            href="https://www.notion.so/ctrl-plus-y/CTRL-y-Open-Positions-cc3896a8f9a84e97a6383bbb9dba6f585"
            target="_blank">
          <i>Sign Up!</i>
        </a>
      </div>
    </div>
    <div class="about-img-container" data-aos="fade-up">
      <img
          class="svg-filter"
          src="../assets/zee.svg"
      />
    </div>
  </section>
</template>

<script>
export default {

}
</script>

<style scoped>
.about-section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 2em 1em;
  text-size-adjust: 100%;
  min-height: 800px;
}

.about-title {
  color: black;
  font-size: 3em;
  text-align: center;
  text-size-adjust: 100%;
}

.about-description {
  color: black;
  font-size: 1.2em;
  line-height: 1.6em;
  margin-top: 1em;
  text-align: left;
  max-width: 600px; /* To keep the line length comfortable to read */
  text-size-adjust: 100%;
}

.cta-button-container {
  display: flex;
  justify-content: center;
  margin-top: 1.5em;
  text-size-adjust: 100%;
}

.cta-button {
  background-color: orange;
  border: none;
  border-radius: 2em;
  color: black;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2em;
  padding: 1em 2em;
  text-decoration: none; /* Since it's a link now, not a button */
  transition: all 0.3s ease;
  text-size-adjust: 100%;
}

.cta-button i {
  margin-right: 0.5em;
}

.cta-button:hover {
  background-color: orange;
  color: black;
  transform: scale(1.05); /* Added scale effect on hover */
}

.cta-button:active {
  background-color: black;
  color: black;
}

.content-container {
  margin-bottom: 3em;
}

.about-image-container img {
  width: 100%;
  height: auto;
  text-size-adjust: 100%;
}

.svg-filter{
  filter: drop-shadow(3px 5px 2px rgb(0 0 0 / 0.4));
  max-height: 400px;
}

@media (min-width: 768px) {
  .about-section {
    flex-direction: row;
    justify-content: space-around;
    text-size-adjust: 100%;
  }

  .content-container {
    margin-bottom: 0;
    width: 45%;
    text-size-adjust: 100%;
  }
}
</style>