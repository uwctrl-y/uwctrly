<template>
  <section>
    <div class="introduction-section">
      <div class="intro-left">
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
    <div class="paintbrush-graphic" ref="graphicBox">
      <div :style="{ transform: `translateY(${graphicParallax}px)` }">
        <img class="svg-paintbrush" ref="graphic" src="../assets/paintbrushGraphic.svg" />
      </div>
    </div>

  </section>
</template>

<script>
import SlidingTextIntroduction from './SlidingTextIntroduction.vue';

export default {
  mounted() {
    window.addEventListener('scroll', this.graphicParallaxEffect);
  },
  methods: {
    graphicParallaxEffect(event) {
      // The graphic is responsive, adjust the max height of the surrounding container depending on the graphic's height
      const heightOfGraphic = this.$refs.graphic.offsetHeight
      this.$refs.graphicBox.style.maxHeight = (0.65 * heightOfGraphic) + 'px'

      const scrollY = window.scrollY;
      // Start the animation a bit later so the graphic doesnt entirely translate out of view
      if (this.reachedIntro) this.graphicParallax = this.graphicParallax + ((scrollY - this.prevScrollY) * -0.3);

      this.prevScrollY = scrollY;
    },
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.graphicParallaxEffect);
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
      graphicParallax: 400,
      prevScrollY: 0
    };
  },
}
</script>

<style scoped>
.introduction-section {
  color: #E4E4D0;
  display: flex;
  justify-content: space-between;
  padding: 103px 40px 197px 40px;
  background-color: #09702C;
}

.intro-left {
  width: max-content;
}

.intro-right {
  width: 70%;
}

.section-title {
  font-size: 30px;
  font-weight: 500;
  line-height: calc(5vw + 10px);
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
  width: calc(100% - 80px);
  height: fit-content;
  max-height: calc(0.54*(100vw - 80px));
  overflow: hidden;
  position: relative;
  text-align: center;
  margin: 40px;
  border-radius: 10px;
}

.svg-paintbrush {
  width: 100%;
  max-width: 99vw;
}

@media screen and (max-width: 1150px) {
  .section-title {
    font-size: 25px;
  }
}

@media screen and (max-width: 900px) {
  .introduction-section {
    flex-direction: column;
    padding-bottom: 80px;
  }

  .intro-left {
    width: 100%;
    margin-bottom: 10px;
  }

  .intro-right {
    width: 100%;
  }

  .section-title {
    line-height: 1em;
    font-size: 20px;
    letter-spacing: -1px;
  }
}

@media screen and (max-width: 600px) {
  .introduction-section {
    padding: 60px 40px 80px 40px;
  }

  .paintbrush-graphic {
    margin: 60px 40px;
    width: calc(100% - 80px);
  }
}

@media screen and (max-width: 500px) {
  .section-title {
    font-size: 12px;
    letter-spacing: -0.5px;
  }

  .intro-left {
    margin-bottom: 0;
  }
}

@media screen and (max-width: 350px) {
  .introduction-section {
    padding-top: 40px;
  }

}
</style>