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
    if (visualViewport >= 700) {
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
    }
    else {
      const sentenceString1 = "WOULD YOU LIKE...TO DESIGN THE FUTURE"
      const sentenceArray1 = sentenceString1.split(" ").map(string => ({ content: string}))
      return {
        heading1: sentenceArray1,
        sectionClass1: 'section-heading1',
        animatedWordClass: 'animated-word',
      };
    }
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
  margin-bottom: -2px;
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
    transition: opacity 2s, transform 1s; 
  }

.pre-intro-1 {
  margin-left: -12%;
}

.pre-intro-2 {
  margin-left: 50%;
}

.pre-intro-3 {
  margin-left: 15%;
}

@media screen and (max-width: 1400px) {
  .eyes {
    transform: scale(0.9);
    margin-top: 12vh;
    margin-left: -17vw;
  }
}
@media screen and (max-width: 1300px) {
  .eyes {
    transform: scale(0.8);
    margin-top: 10vh;
    margin-left: -18vw;
  }
}

@media screen and (max-width: 1100px) {
  .eyes {
    transform: scale(0.7);
    margin-top: 10vh;
    margin-left: -20vw;
  }
}

@media screen and (max-width: 1000px) {
  .pre-introduction-section {
    margin-top: -275px;
    padding-top: 10px;
    padding-bottom: 10px;
    justify-content:flex-start;
    margin-right: auto;
    padding-right: 83px;
    padding-left: 83px;
  }
  .pre-intro-1, .pre-intro-2, .pre-intro-3 {
    margin-left: 0px;
  }

  .eyes {
    transform: scale(0.55);
    margin-top: 32vh;
    margin-left: 55vw;
  }
}

@media screen and (max-width: 900px) {
  .pre-introduction-section {
    margin-top: -250px;
  }
}
@media screen and (max-width: 800px) {
  .eyes {
    display: none;
  }
  .section-heading {
    /* flex-wrap: wrap; */
    margin-right: -100px;
  } 
  .pre-introduction-section {
    margin-top: -200px;
    margin-bottom: -90px;
    padding-top: 40px;
  }
}

@media screen and (max-width: 600px) {
  .pre-introduction-section {
    padding: 60px 40px 80px 40px;
    margin-top: -150px
  }
}

@media screen and (max-width: 600px) {
  .pre-introduction-section {
    margin-bottom: -100px;
  }
}


</style>
