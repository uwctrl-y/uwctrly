<template>
  <section>
    <div class="pre-introduction-section">
      <div :class="sectionHeadingClass">
        <SlidingTextPreIntroduction class="pre-intro-1"
            :heading="heading1"
            :sectionClass="sectionClass"
            :animatedWordClass="animatedWordClass"
            v-if="reachedIntro"
        />
        
        <SlidingTextPreIntroduction class="pre-intro-2"
            :heading="heading2"
            :sectionClass="sectionClass2"
            :animatedWordClass="animatedWordClass"
            v-if="reachedIntro"
        />
        
        <SlidingTextPreIntroduction class="pre-intro-3"
            :heading="heading3"
            :sectionClass="sectionClass3"
            :animatedWordClass="animatedWordClass"
            v-if="reachedIntro"
        />
      </div>
      <img :class="{ 'fade-in': reachedIntro }" class="eyes" src="../assets/preIntroduction/eyes.svg" />
    </div>
  </section>
</template>


<script>
import SlidingTextPreIntroduction from "@/views/SlidingTextPreIntroduction.vue";

export default {
  components: { SlidingTextPreIntroduction },
  props: ['reachedIntro'],
  data() {
    const sentenceString1 = "WOULD YOU LIKE..."
    const sentenceArray1 = sentenceString1.split(" ").map(string => ({ content: string,}))
    const sentenceString2 = "TO DESIGN"
    const sentenceArray2 = sentenceString2.split(" ").map(string => ({ content: string,}))
    const sentenceString3 = "THE FUTURE?"
    const sentenceArray3 = sentenceString3.split(" ").map(string => ({ content: string, italic: string === "FUTURE?"}))
    return {
      heading1: sentenceArray1,
      heading2: sentenceArray2,
      heading3: sentenceArray3,
      sectionClass1: 'section-heading1',
      animatedWordClass: 'animated-word',
      sectionClass2: 'section-heading2',
      sectionClass3: 'section-heading3'
    };
  },
  computed: {
    sectionHeadingClass() {
      // Add additional classes or modify the existing class as needed
      return 'section-heading1 custom-class', 'section-heading2 custom-class', 'section-heading3 custom-class';
    },
  },
}
</script>

<style>
.pre-introduction-section {
  transition: opacity 0.5s, transform 0.5s, background-color 0.5s;
  background-color: #09702C;
  color: #E4E4D0;
  font-style: normal;
  display: flex;
  margin-top: -45vh;
  justify-content: center;
  align-items: center;
  min-height: 400px;
  padding-bottom: 10vh;
  column-gap: 20px;
}

.eyes {
  /* margin-top:-100%; */
  /* margin-left: 20%; */
  /* margin-left: 20vw; */
  /* margin-left: -55vw; */
  /* z-index: -1; */
  /* margin-top: 11vh; */
  position: absolute;
  /* left: 35%;
  top: 1260px; */
  margin-left: -15vw;
  margin-top: 15vh;
  opacity: 0;
}

.fade-in {
    opacity: 1;
    transform: translateY(-20px);
    transition: opacity 2s, transform 1s; /* Transition duration for the fade effect */
  }

/* Add your desired styles here */
.pre-intro-1 {
  margin-left: -15%;
}

.pre-intro-2 {
  margin-left: 50%;
}

.pre-intro-3 {
  margin-left: 15%;
}



</style>
