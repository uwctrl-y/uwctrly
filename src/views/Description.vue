<template>
    <section class="description-section">
      <div class="content-container" data-aos="fade-up">
        <div class="description-intro">
          <h1 class="description-title">What's Going Down</h1>
          <svg class="description-divider" width="71" height="71" viewBox="0 0 71 71" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M35.5001 71C40.8306 71 44 67.1485 44 62.97C44 59.4353 38.5995 46.306 36.4079 41.1235C36.0663 40.3157 34.942 40.3191 34.6048 41.1288C32.4213 46.3714 27 59.7157 27 62.97C27 67.1485 30.1695 71 35.5001 71Z" fill="#09702C"/>
          <path d="M4.25011 53.3613C6.9154 57.9777 11.8356 58.7967 15.4542 56.7075C18.5154 54.9401 27.1855 43.6984 30.5778 39.2092C31.1066 38.5094 30.5415 37.5375 29.6717 37.6503C24.0397 38.3807 9.77253 40.3579 6.95423 41.985C3.33556 44.0743 1.58482 48.7449 4.25011 53.3613Z" fill="#09702C"/>
          <path d="M4.25011 17.3614C6.9154 12.745 11.8356 11.926 15.4542 14.0152C18.5154 15.7825 27.1855 27.0242 30.5778 31.5134C31.1066 32.2132 30.5415 33.1851 29.6717 33.0723C24.0397 32.342 9.77253 30.3648 6.95423 28.7376C3.33556 26.6484 1.58482 21.9778 4.25011 17.3614Z" fill="#09702C"/>
          <path d="M35.4999 6.89956e-07C30.1694 1.12264e-06 27 3.85152 27 8.02996C27 11.5647 32.4005 24.694 34.5921 29.8765C34.9337 30.6843 36.058 30.6809 36.3952 29.8712C38.5787 24.6286 44 11.2843 44 8.02996C44 3.85149 40.8305 2.5727e-07 35.4999 6.89956e-07Z" fill="#09702C"/>
          <path d="M66.7499 17.6387C64.0846 13.0223 59.1644 12.2033 55.5458 14.2925C52.4846 16.0599 43.8145 27.3016 40.4222 31.7908C39.8934 32.4906 40.4585 33.4625 41.3283 33.3497C46.9603 32.6193 61.2275 30.6421 64.0458 29.015C67.6644 26.9257 69.4152 22.2551 66.7499 17.6387Z" fill="#09702C"/>
          <path d="M66.7499 53.6386C64.0846 58.255 59.1644 59.074 55.5458 56.9848C52.4846 55.2174 43.8145 43.9758 40.4222 39.4866C39.8934 38.7868 40.4585 37.8149 41.3283 37.9277C46.9603 38.658 61.2275 40.6352 64.0458 42.2624C67.6644 44.3516 69.4152 49.0222 66.7499 53.6386Z" fill="#09702C"/>
          </svg>
          <p class="description-subheading">What will our event entail?</p>
        </div>
        <div class="row">
          <div class="panel" :style="{ transform: `translateY(${panel1Parallax}px)` }">
            <img class="panel-img" src="../assets/descriptionPanel1.png" alt="Image 1">
            <div class="panel-content">
                <h1 class="panel-heading">48 hours</h1>
                <p class="panel-text">Design a solution to the given problem in a weekend.</p>
            </div>
          </div>
          <div class="panel" :style="{ transform: `translateY(${panel2Parallax}px)` }">
            <img class="panel-img" src="../assets/descriptionPanel2.png" alt="Image 2">
            <div class="panel-content">
                <h1 class="panel-heading">No coding involved.</h1>
                <p class="panel-text">Ideation and UI/UX design on Figma only!</p>
            </div>
          </div>
          <div class="panel" :style="{ transform: `translateY(${panel3Parallax}px)` }">
            <img class="panel-img" src="../assets/descriptionPanel3.png" alt="Image 3">
            <div class="panel-content">
                <h1 class="panel-heading">Offline.</h1>
                <p class="panel-text">Join us for our in-person event at the University of Waterloo</p>
            </div>
          </div>
        </div>
      </div>
    </section>
</template>

<script>
export default {
  data() {
    return {
      panel1Parallax: -100,
      panel2Parallax: 450,
      panel3Parallax: 1000,
      prevScrollDirection: 0
    };
  },
  mounted() {
    window.addEventListener('scroll', this.Parallax);
  },
  methods: {
    Parallax(event) {
      const scroll = window.scrollY;
      const scrollDirection = event.deltaY > 0 ? 1 : -1;
      const scrollDiff = scroll - this.prevScrollDirection;
      this.prevScrollDirection = scroll;

      this.panel1Parallax += scrollDiff * -0.03 * scrollDirection;
      this.panel2Parallax += scrollDiff * 0.1 * scrollDirection;
      this.panel3Parallax += scrollDiff * 0.23 * scrollDirection;
    },
  },
  beforeDestroy() {
    window.removeEventListener('wheel', this.Parallax);
  }
}

</script>

<style scoped>
  .description-section {
  display: flex;
  text-align: center;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 2em 1em;
  text-size-adjust: 100%;
  min-height: 800px;
  margin-top: 200px;
  overflow: visible;
}
 .description-title {
    color: #09702C;
    text-align: center;
    font-size: 11.25rem;
    font-style: normal;
    font-weight: 500;
    line-height: 11.25rem; /* 100% */
    letter-spacing: -0.5625rem;
    text-transform: uppercase;
    text-size-adjust: 100%;
  }
  .description-intro {
    display: inline-flex;
    flex-direction: column;
    align-items: center;
    gap: 1.8125rem;
    margin: 0 1px;
  }
  
  .description-divider {
    margin-bottom: 30px;
  }
  .description-subheading {
    color: #09702C;
    font-size: 30px;
    font-style: normal;
    font-weight: 400;
    line-height: 40px;
    letter-spacing: -1.5px;
    /* margin-bottom: 447px; */
    margin-bottom: 109px;
  }
  .panel {
    width: panel-img;
    display: inline-flex;
    flex-direction: column;
    justify-content: baseline;
    align-items: flex-start;
    text-align: start;
    gap: 20px;
    width: 30%;
    position: relative;
    /* scroll-snap-align: start; */
    z-index: 1;
    transition: transform 0.05s;
  }
  /* .panel:nth-child(2) {
      transform: translateY(169px);
    }
    .panel:nth-child(3) {
        transform: translateY(338px);
    } */

  .row {
    display: flex;
    flex-direction: row;
    justify-content:space-between;
    gap: 60px;
    height: 150vh;
    /* overflow-x: scroll; */
    /* perspective: 1px; */
    scroll-snap-type: y mandatory;
  }
  
  .panel img {
    width: 100%;
  }

  .panel-content {
    display: flex;
    padding: 20px;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    gap: 12px;
  }
  .panel-heading {
    color: #09702C;
    /* font-family: Roboto; */
    font-size: 84px;
    font-style: normal;
    font-weight: 500;
    line-height: 90px;
    letter-spacing: -4.2px;
    text-size-adjust: 100%;
  }
  
  .panel-text {
    color: #09702C;
    /* font-family: Roboto; */
    font-size: 30px;
    font-style: normal;
    font-weight: 400;
    line-height: 40px;
    letter-spacing: -1.5px;
  }
</style>
  