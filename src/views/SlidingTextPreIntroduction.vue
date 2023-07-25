<template>
  <div :class="sectionClass">
    <div class="section-heading">
      <span v-for="(word, index) in heading" :key="index" :class="animatedWordClass">
        <p v-if="!word.italic">{{ word.content }}</p>
        <p v-else><i>{{ word.content }}</i></p>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  props: ['heading', 'sectionClass', 'animatedWordClass'],
  mounted() {
    const animatedLetters = this.$el.querySelectorAll(".animated-word");

    setTimeout(() => {

      animatedLetters.forEach((letter, index) => {
        setTimeout(() => {
          letter.style.opacity = "1";
          letter.style.transform = "translateY(0)";
        }, index * 100);
      });
    }, 500); // Adjust the delay before animation starts as per your preference
  },
};
</script>

<style scoped>
.section-heading {
  padding-top: 10vh;
  color: #E4E4D0;
  font-size: 8rem;
  font-style: normal;
  font-weight: 500;
  line-height: 11vh;
  text-transform: uppercase;
  text-align: center;
  width: 70vw;
}

.animated-word {
  display: inline-block;
  opacity: 0;
  transform: translateY(100%);
  transition: opacity 0.5s, transform 0.5s;
  /* Add your desired styles here */
}

/* Add additional styles for the paragraph and italic elements if needed */
.animated-word p {
  /* Styles for non-italic words */
  display: flex;
  align-items: center;
  color: #E4E4D0;
  font-size: 6rem;
  font-style: normal;
  font-weight: 600;
}

.animated-word p i {
  /* Styles for italic words */
}
</style>