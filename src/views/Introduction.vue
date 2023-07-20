<template>
  <section style="background-color: #09702C;">
    <div class="introduction-section">
      <div class="intro-left">
        <p class="section-number">01.</p>
        <p class="section-title">About CTRL + y</p>
      </div>
      <div class="intro-right">
        <SlidingTextIntroduction :heading="heading" :paragraph="paragraph" v-if="reachedIntro" />
        <p class="section-heading" v-else>
          Imagine the future at CTRL + y
        </p>
        <p class="section-content" v-if="!reachedIntro">{{ paragraph }}</p>
      </div>
    </div>
    <div class="paintbrush-graphic" ref="background">

      <img class="svg-paintbrush" src="../assets/paintbrushGraphic.svg" />

    </div>

  </section>
</template>

<script>
import SlidingTextIntroduction from './SlidingTextIntroduction.vue';

export default {
  mounted() {
    document.addEventListener('scroll', this.handleScroll)
  },
  unmounted() {
    document.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll(evt) {
      const scrollY = window.scrollY - 1900

      const maxBackgroundSize = 120
      const backgroundSize = scrollY / (maxBackgroundSize - 100) // increases as user scrolls

      // zoom the background at a slower rate
      this.$refs.background.style.transform =
        'scale(' + (100 + backgroundSize * 0.1) / 100 + ')'
    }

  },
  components: { SlidingTextIntroduction },
  props: ['reachedIntro'],
  data() {
    const headingString = "Imagine the future at CTRL + y"
    const headingArray = headingString.split(" ")
    const paragraph = ["The rising popularity of emerging technologies (such as artificial intelligence and artificial reality) pose a new type of design challenge to UI/UX designers. Aspiring UI/UX designers, in particular, may find this challenge difficult due to limited experience in these fields and scarce resources to reference.", "A group of students came together to present a solution to this issue. The designathon was dubbed CTRL + y in honour of the popular keyboard shortcut for ‘redo.’ It symbolizes how we’re taking the resources of the past to design the future."]
    return {
      heading: headingArray,
      paragraph: paragraph,
    };
  },
}
</script>

<style scoped>
.introduction-section {
  color: #E4E4D0;
  display: flex;
  justify-content: space-between;
  padding: 103px 83px 197px 83px;
}

.intro-left {
  width: 210px;
}

.intro-right {
  width: 55%;
}

.section-number {
  font-size: 20px;
  font-weight: 500;
  line-height: 30px;
  letter-spacing: -1px;
}

.section-title {
  font-size: 30px;
  font-weight: 500;
  line-height: 30px;
  letter-spacing: -1.5px;
}

.section-heading {
  font-size: 84px;
  font-weight: 500;
  line-height: 94px;
  letter-spacing: -4.2px;
  overflow: hidden;
  display: flex;
  flex-wrap: wrap;
}

.section-content {
  margin-top: 60px;
  font-size: 30px;
  font-weight: 400;
  line-height: 40px;
  letter-spacing: -1.5px;
}

.paintbrush-graphic {
  width: 100%;
  height: fit-content;
  overflow: hidden;
  padding: 40px;
  position: relative;
}

.svg-paintbrush {
  width: 100%;
}

@media screen and (max-width: 900px) {
  .introduction-section {
    flex-direction: column;
    padding-bottom: 80px;
  }  
  .intro-left {
    width: 100%;
    margin-bottom: 40px;
  }

  .intro-right {
    width: 100%;
  }
}

@media screen and (max-width: 600px) {
  .introduction-section {
    padding: 60px 40px 80px 40px;
  }

  .paintbrush-graphic {
    padding: 20px;
  }
}

@media screen and (max-width: 400px) {
  .introduction-section {
    padding-bottom: 20px;
  }
  .section-number {
    font-size: 15px;
    letter-spacing: -.5px;
  }

  .section-title {
    font-size: 25px;
    letter-spacing: -1px;
  }
} 

@media screen and (max-width: 350px) {
  .introduction-section {
    padding-top: 40px;
  }

  .intro-left {
    margin-bottom: 20px;
  }
  .section-title {
    font-size: 18px;
  }

}

</style>