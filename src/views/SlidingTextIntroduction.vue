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
    }, 1500); // Adjust the delay before animation starts as per your preference

    setTimeout(() => {
    animatedParagraphs.forEach((par, index) => {
        setTimeout(() => {
          par.style.opacity = "1";
          par.style.transform = "translateY(0)";
        }, index * 500);
      });
    }, 1000 +(animatedLetters.length * 100)); // Adjust the delay before animation starts as per your preference
  },
};
</script>

<style>
.headingText {
  position: relative;
  font-size: 5vw;
  font-weight: 500;
  line-height: calc(5vw + 10px);
  letter-spacing: -4.2px;
  display: flex;
  flex-wrap: wrap;
  column-gap: 15px;
}

.paragraphText {
  margin-top: 60px;
  font-size: 2vw;
  font-weight: 400;
  line-height: calc(2vw + 6px);
  letter-spacing: -0.07vw;
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

@media screen and (max-width: 1150px) {
  .paragraphText {
    margin-top: 2em;
  }
}

@media screen and (max-width: 900px) {
  .headingText {
    font-size: 7vw;
    letter-spacing: -3px;
  }

  .paragraphText {
    font-size: 2.5vw;
    line-height: calc(2.5vw + 6px);
  }
}

@media screen and (max-width: 650px) {
  .headingText {
    font-size: 6vw;
    letter-spacing: -2.5px;
  }

  .paragraphText {
    font-size: 2.5vw;
    line-height: calc(2.5vw + 6px);
  }
}

@media screen and (max-width: 500px) {
  .headingText {
    font-size: 5.5vw;
    letter-spacing: -1.5px;
    column-gap: 8px;
  }

  .paragraphText {
    letter-spacing: -0.5px;
    margin-top: 30px;
    font-size: 3vw;
  }

  .animated-paragraphs {
    margin-bottom: 15px;
  }
}
</style>