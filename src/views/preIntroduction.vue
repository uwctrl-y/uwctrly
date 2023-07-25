<template>
  <section>
    <div class="pre-introduction-section">
      <div :class="sectionHeadingClass">
        <SlidingTextPreIntroduction
            :heading="heading"
            :sectionClass="sectionClass"
            :animatedWordClass="animatedWordClass"
            v-if="reachedIntro"
        />
      </div>
    </div>
  </section>
</template>


<script>
import SlidingTextPreIntroduction from "@/views/SlidingTextPreIntroduction.vue";

export default {
  components: { SlidingTextPreIntroduction },
  props: ['reachedIntro'],
  data() {
    const sentenceString = "WOULD YOU LIKE...TO DESIGN THE FUTURE?"
    const sentenceArray = sentenceString.split(" ").map(string => ({ content: string, italic: string === "FUTURE"}))
    return {
      heading: sentenceArray,
      sectionClass: 'section-heading',
      animatedWordClass: 'animated-word'
    };
  },
  computed: {
    sectionHeadingClass() {
      // Add additional classes or modify the existing class as needed
      return 'section-heading custom-class';
    },
  },
}
</script>

<style>
.pre-introduction-section {
  background-color: #09702C;
  color: #E4E4D0;
  font-style: normal;
  display: flex;
  margin-top: -45vh;
  justify-content: center;
  align-items: center;
  min-height: 400px;
  padding-bottom: 10vh;
}

.eyes-img img {
  width: 100%;
  height: 100%;
}

/* Add your desired styles here */
.custom-class {
  /* Custom styles for the section-heading class */
}
</style>
