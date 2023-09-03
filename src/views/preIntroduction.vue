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
      <img :class="{ 'fade-in': reachedIntro, 'shake-on-hover': opacityTransitionCompleted }" class="eyes" src="../assets/preIntroduction/eyes.svg" @transitionend="handleTransitionEnd" />
    </div>
  </section>
</template>


<script>
import SlidingTextPreIntroduction from "@/views/SlidingTextPreIntroduction.vue";

export default {
  components: { SlidingTextPreIntroduction },
  props: ['reachedIntro'],
  data() {
    if (window.innerWidth >= 700) {
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
        sectionClass3: 'section-heading3',
        opacityTransitionCompleted: false
      };
    }
    else {
      const sentenceString1 = "WOULD YOU LIKE...TO DESIGN THE FUTURE?"
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
    methods: {
        handleTransitionEnd() {
            this.opacityTransitionCompleted = true;
        },
    }
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
  padding-top: 5vh;
  margin-bottom: -2px;
}

.eyes {
  position: absolute;
  margin-left: -4vw;
  margin-top: 9vh;
  opacity: 0;
}

.fade-in {
    opacity: 1;
    //transform: translateY(-20px);
    transition: opacity 2s, transform 1.5s;
    animation: shake 3s
}

.shake-on-hover:hover{
    animation: shake 0.5s;
    animation-iteration-count: infinite;
}
@keyframes shake {
    0%, 100% { transform: rotate(0deg); }
    10%, 90% { transform: rotate(-2deg); } /* Increased rotation angles */
    20%, 80% { transform: rotate(2deg); }  /* Increased rotation angles */
    30%, 70% { transform: rotate(0deg); }
    40%, 60% { transform: rotate(2deg); }  /* Increased rotation angles */
    50% { transform: rotate(-2deg); }       /* Increased rotation angles */
}

.pre-intro-1 {
  margin-left: -10%;
}

.pre-intro-2 {
  margin-left: 58%;
}

.pre-intro-3 {
  margin-left: 18%;
}

@media screen and (max-width: 1600px) {
  .eyes {
    width: 200px;
    margin-top: 10vh;
    margin-left: -21vw;
  }
  .pre-intro-1 {
      margin-left: -10%;
  }
  .pre-intro-2 {
      margin-left: 45%;
  }
  .pre-intro-3 {
      margin-left: 11.5%;
  }

}
@media screen and (max-width: 1300px) {
  .eyes {
    width: 180px;
    margin-top: 10vh;
    margin-left: -28vw;
  }
  .pre-introduction-section {
    margin-top: -30vh;
  }
}

@media screen and (max-width: 1100px) {
  .eyes {
    margin-top: 6vh;
    margin-left: -30vw;
  }
}

@media screen and (max-width: 1000px) {
  .pre-introduction-section {
    padding-bottom: 10px;
    justify-content:flex-start;
    margin-right: auto;
    padding-right: 83px;
    padding-left: 83px;
  }
  .pre-intro-1, .pre-intro-2, .pre-intro-3 {
    margin-left: -45px;
  }
  .eyes {
    margin-top: 12vh;
    margin-left: 55vw;
  }
}

@media screen and (max-width: 900px) {
  .pre-introduction-section {
    margin-top: -28vh;
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
    margin-top: -22vh;
    margin-bottom: -90px;
    padding-top: 40px;
  }
}

@media screen and (max-width: 700px) {
  .pre-introduction-section {
    margin-top: -18vh;
  }
}

@media screen and (max-width: 600px) {
  .pre-introduction-section {
    margin-top: -15vh;
    padding-bottom: 50px;
  }
}

@media screen and (max-width: 500px) {
  .pre-introduction-section {
    margin-top: -12vh;
  }
}

@media screen and (max-width: 400px) {
  .pre-introduction-section {
    margin-top: -70px
  }
}


</style>
