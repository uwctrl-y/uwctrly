<template>
  <section class="introduction-section">
    <div class="intro-left">
      <p class="section-number">01.</p>
      <p class="section-title">introducing CTRL + y</p>
    </div>
    <div class="intro-right">
        <SlidingTextIntroduction/>
      <!-- <p class="section-heading">We aim to foster <i>innovative design solutions</i> for emerging technologies.</p> -->
      <p class="section-content">
        The rising popularity of emerging technologies (such as artificial intelligence and
        artificial reality) pose a new type of design challenge to UI/UX designers. Aspiring
        UI/UX designers, in particular, may find this challenge difficult due to limited
        experience in these fields and scarce resources to reference. A group of Waterloo
        students came together to present a solution to this issue. The designathon was dubbed
        CTRL + y in honour of the popular keyboard shortcut for ‘redo.’ It symbolizes how we’re
        taking the resources of the past to design the future.
      </p>
    </div>
  </section>
</template>

<script>
import SlidingTextIntroduction from './SlidingTextIntroduction.vue';

export default {
  components: { SlidingTextIntroduction },
  data() {
    return {
      heading: [{
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
}
</script>

<style scoped>
.introduction-section {
  background-color: #09702C;
  color: #E4E4D0;
  font-family: Roboto;
  font-style: normal;
  display: flex;
  justify-content: space-between;
}

.intro-left {
  width: 15%;
}

.intro-right {
  width: 60%;
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

.section-content {
  margin-top: 60px;
  font-size: 30px;
  font-weight: 400;
  line-height: 40px;
  letter-spacing: -1.5px;
}
</style>