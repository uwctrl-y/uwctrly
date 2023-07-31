<template>
  <div>
    <div class="headingText">
      <span v-for="(word, index) in heading" :key="index" class="animated-word">
        <p v-if="!word.italic">{{ word.content }}</p>
        <p v-else><i>{{ word.content }}</i></p>
      </span>
    </div>
    <p class="paragraphText">{{ paragraph }}</p>
  </div>
</template>

<script>
export default {
  props: ['heading', 'paragraph'],
  mounted() {
    const animatedLetters = this.$el.querySelectorAll(".animated-word");
    const animatedParagraph = this.$el.querySelectorAll(".paragraphText")[0];

    setTimeout(() => {

      animatedLetters.forEach((letter, index) => {
        setTimeout(() => {
          letter.style.opacity = "1";
          letter.style.transform = "translateY(0)";
        }, index * 100);
      });

      setTimeout(() => {
        animatedParagraph.style.opacity = "1";
        animatedParagraph.style.transform = "translateY(0)";
      }, 100);

    }, 1500); // Adjust the delay before animation starts as per your preference
  },
};
</script>

<style>
.headingText {
  position: relative;
  font-size: 84px !important;
  font-weight: 500;
  line-height: 94px;
  letter-spacing: -4.2px;
  overflow: hidden;
  display: flex;
  flex-wrap: wrap;
  column-gap: 15px;
}

.paragraphText {
  margin-top: 60px;
  font-size: 30px;
  font-weight: 400;
  line-height: 40px;
  letter-spacing: -1.5px;
  opacity: 0;
  transform: translateY(100%);
  transition: opacity 0.5s, transform 0.5s;
}

.animated-word {
  display: inline-block;
  opacity: 0;
  transform: translateY(100%);
  transition: opacity 0.5s, transform 0.5s;
  height: max-content;
}
</style>