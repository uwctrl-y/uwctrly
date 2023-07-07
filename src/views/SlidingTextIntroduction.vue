<template>
  <div>
    <div id="headingText">
      <span v-for="(word, index) in text" :key="index" class="animated-word">
        <p v-if="word.italic">{{ word.content }}</p>
        <p v-else><i>{{ word.content }}</i></p>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: [{
        content: 'We',
        italic: true,
      }, {
        content: 'aim',
        italic: true,
      }, {
        content: 'to',
        italic: true,
      }, {
        content: 'foster',
        italic: true,
      }, {
        content: 'innovative',
        italic: false
      }, {
        content: 'design',
        italic: false
      }, {
        content: 'solutions',
        italic: false
      }, {
        content: 'for',
        italic: true,
      }, {
        content: 'emerging',
        italic: true,
      }, {
        content: 'technologies',
        italic: true,
      }],
    };
  },
  mounted() {
    const animatedLetters = this.$el.querySelectorAll(".animated-word");

    setTimeout(() => {
      animatedLetters.forEach((letter, index) => {
        setTimeout(() => {
          letter.style.opacity = "1";
          letter.style.transform = "translateY(0)";
        }, index * 100); // Adjust the delay as per your preference
      });
    }, 500); // Adjust the delay before animation starts as per your preference
  },
};
</script>

<style>
#headingText {
  position: relative;
  font-size: 84px!important;
  font-weight: 500;
  line-height: 94px;
  letter-spacing: -4.2px;
  overflow: hidden;
  display: flex;
  flex-wrap: wrap;
  column-gap: 15px;
}

.animated-word {
  display: inline-block;
  opacity: 0;
  transform: translateY(100%);
  transition: opacity 0.5s, transform 0.5s;
  height: max-content;
}
</style>