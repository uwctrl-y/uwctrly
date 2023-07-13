<!-- this is just an example of what the text loading we might want?-->
<!-- could be something else, charissa will need to verify -->

<template>
  <div ref="slidingText">
    <div id="loadingText">
      <span v-for="(letter, index) in text" :key="index" class="animated-letter">
        {{ letter }}
      </span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: "Loading...",
    };
  },
  mounted() {
    const animatedLetters = this.$el.querySelectorAll(".animated-letter");

    setTimeout(() => {
      animatedLetters.forEach((letter, index) => {
        setTimeout(() => {
          letter.style.opacity = "1";
          letter.style.transform = "translateY(0)";
        }, index * 100); // Adjust the delay as per your preference
      });
    }, 500); // Adjust the delay before animation starts as per your preference
    console.log(this.$refs.slidingText.offsetHeight)
  },
};
</script>

<style>
#loadingText {
  position: relative;
  font-size: 36px;
  overflow: hidden;
}

.animated-letter {
  display: inline-block;
  opacity: 0;
  transform: translateY(100%);
  transition: opacity 0.5s, transform 0.5s;
}
</style>