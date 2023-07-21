<template>
  <div>
    <div class="headingText">
      <span v-for="(word, index) in heading" :key="'heading_' + index" class="animated-word">
        <p>{{ word }}</p>
      </span>
    </div>
    <div class="paragraphText">
      <span v-for="(par, index) in paragraph" :key="'paragraph_' + index" class="animated-paragraphs">
        <p>{{ par }}</p>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  props: ['heading', 'paragraph'],
  mounted() {
    const animatedLetters = this.$el.querySelectorAll(".animated-word");
    const animatedParagraphs = this.$el.querySelectorAll(".animated-paragraphs");

    
    setTimeout(() => {
      animatedLetters.forEach((letter, index) => {
        setTimeout(() => {
          letter.style.opacity = "1";
          letter.style.transform = "translateY(0)";
        }, index * 100);
      });
    }, 500); // Adjust the delay before animation starts as per your preference

    setTimeout(() => {
    animatedParagraphs.forEach((par, index) => {
        setTimeout(() => {
          par.style.opacity = "1";
          par.style.transform = "translateY(0)";
        }, index * 500);
      });
    }, 500+(animatedLetters.length * 100)); // Adjust the delay before animation starts as per your preference
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
  /* overflow: hidden; */
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
}

.animated-word {
  display: inline-block;
  opacity: 0;
  transform: translateY(100%);
  transition: opacity 0.5s, transform 0.5s;
  height: max-content;
}

.animated-paragraphs {
  display: inline-block;
  opacity: 0;
  transform: translateY(100%);
  transition: opacity 0.5s, transform 0.5s;
  margin-bottom: 30px;
}

@media screen and (max-width: 1070px) {
  .headingText {
    font-size: 74px !important;
    line-height: 84px;
  }
}

@media screen and (max-width: 715px) {
  .headingText {
    font-size: 64px !important;
    line-height: 74px;
  }

  .paragraphText {
    font-size: 25px;
    line-height: 35px;
  }
}

@media screen and (max-width: 400px) {
  .headingText {
    font-size: 34px !important;
    line-height: 44px;
    letter-spacing: -2px;
    column-gap: 8px;
  }

  .paragraphText {
    font-size: 15px;
    line-height: 25px;
    letter-spacing: -0.5px;
    margin-top: 30px;
  }

  .animated-paragraphs {
    margin-bottom: 15px;
  }
}
</style>