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
    }, 400); // Adjust the delay before animation starts as per your preference
  },
};
</script>

<style scoped>
.section-heading {
  padding-top: 10vh;
  color: #E4E4D0;
  font-style: normal;
  font-weight: 500;
  line-height: 8vh;
  text-transform: uppercase;
  text-align: left;
  width: 70vw;
  display: flex;
  column-gap: 40px;
  letter-spacing: -9px;
  padding-right: 80px;
}

.animated-word {
  display: inline-block;
  opacity: 0;
  transform: translateY(100%);
  transition: opacity 0.5s, transform 0.5s;
  height: max-content;
}

/* Add additional styles for the paragraph and italic elements if needed */
.animated-word p {
  /* Styles for non-italic words */
  display: flex;
  align-items: right;
  justify-content: flex-end;
  color: #E4E4D0;
  font-size: 150px;
  font-style: normal;
  font-weight: 500;
}

.animated-word p i {
  font-weight: 500;
}

@media screen and (max-width: 1500px) {
  .animated-word p {
    font-size: 130px;
  }
}

@media screen and (max-width: 1300px) {
  .animated-word p {
    font-size: 120px;
  }
}

@media screen and (max-width: 1200px) {
  .animated-word p {
    font-size: 110px;
  }
}

@media screen and (max-width: 1100px) {
  .animated-word p {
    font-size: 100px;
    letter-spacing: -6.5px;
  }
  .section-heading {
    padding-top: 6vh;
  }
}


@media screen and (max-width: 1000px) {
  .animated-word p {
    font-size: 90px;
    letter-spacing: -6px;
    line-height: 80px;
  }
  .section-heading {
    padding-top: 3vh;
    column-gap: 30px;
    width: 100vw;
  }
}

@media screen and (max-width: 900px) {
  .animated-word p {
    font-size: 80px;
    letter-spacing: -5.5px;
    line-height: 75px;
  }
  
}

@media screen and (max-width: 800px) {
  .animated-word p {
    font-size: 74px;
    letter-spacing: -5.2px;
    line-height: 85px;
  }
  .section-heading {
    padding-top: 0;
    flex-wrap: wrap;
    column-gap: 22px;
  }
}
@media screen and (max-width: 600px) {
  .animated-word p {
    font-size: 64px;
    letter-spacing: -4.5px;
    line-height: 80px;
  }
  .section-heading {
    column-gap: 18px;
  }
}

@media screen and (max-width: 500px) {
  .animated-word p {
    font-size: 52px;
    letter-spacing: -4px;
    line-height: 70px;
  }
}

@media screen and (max-width: 400px) {
  .animated-word p {
    font-size: 44px;
    letter-spacing: -1px;
    line-height: 40px;
  }
}



</style>