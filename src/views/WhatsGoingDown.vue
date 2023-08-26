<template>
    <section class="whats-going-down-section">
      <div class="content-container" data-aos="fade-up">
        <div class="whats-going-down-intro">
          <h1 class="whats-going-down-title">What's Going Down</h1>
          <svg class="whats-going-down-divider" width="71" height="71" viewBox="0 0 71 71" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M35.5001 71C40.8306 71 44 67.1485 44 62.97C44 59.4353 38.5995 46.306 36.4079 41.1235C36.0663 40.3157 34.942 40.3191 34.6048 41.1288C32.4213 46.3714 27 59.7157 27 62.97C27 67.1485 30.1695 71 35.5001 71Z" fill="#09702C"/>
          <path d="M4.25011 53.3613C6.9154 57.9777 11.8356 58.7967 15.4542 56.7075C18.5154 54.9401 27.1855 43.6984 30.5778 39.2092C31.1066 38.5094 30.5415 37.5375 29.6717 37.6503C24.0397 38.3807 9.77253 40.3579 6.95423 41.985C3.33556 44.0743 1.58482 48.7449 4.25011 53.3613Z" fill="#09702C"/>
          <path d="M4.25011 17.3614C6.9154 12.745 11.8356 11.926 15.4542 14.0152C18.5154 15.7825 27.1855 27.0242 30.5778 31.5134C31.1066 32.2132 30.5415 33.1851 29.6717 33.0723C24.0397 32.342 9.77253 30.3648 6.95423 28.7376C3.33556 26.6484 1.58482 21.9778 4.25011 17.3614Z" fill="#09702C"/>
          <path d="M35.4999 6.89956e-07C30.1694 1.12264e-06 27 3.85152 27 8.02996C27 11.5647 32.4005 24.694 34.5921 29.8765C34.9337 30.6843 36.058 30.6809 36.3952 29.8712C38.5787 24.6286 44 11.2843 44 8.02996C44 3.85149 40.8305 2.5727e-07 35.4999 6.89956e-07Z" fill="#09702C"/>
          <path d="M66.7499 17.6387C64.0846 13.0223 59.1644 12.2033 55.5458 14.2925C52.4846 16.0599 43.8145 27.3016 40.4222 31.7908C39.8934 32.4906 40.4585 33.4625 41.3283 33.3497C46.9603 32.6193 61.2275 30.6421 64.0458 29.015C67.6644 26.9257 69.4152 22.2551 66.7499 17.6387Z" fill="#09702C"/>
          <path d="M66.7499 53.6386C64.0846 58.255 59.1644 59.074 55.5458 56.9848C52.4846 55.2174 43.8145 43.9758 40.4222 39.4866C39.8934 38.7868 40.4585 37.8149 41.3283 37.9277C46.9603 38.658 61.2275 40.6352 64.0458 42.2624C67.6644 44.3516 69.4152 49.0222 66.7499 53.6386Z" fill="#09702C"/>
          </svg>
          <p class="whats-going-down-subheading">What will our event entail?</p>
        </div>
        <div class="row">
          <div class="panel" :style="{ transform: `translateY(${panel1Parallax}px)` }">
            <img class="panel-img" src="../assets/whatsGoingDown/whatsGoingDownPanel1.png" alt="Image 1">
            <div class="panel-content">
                <h1 class="panel-heading">48 hours</h1>
                <p class="panel-text">Design a solution to the given problem in a weekend.</p>
            </div>
          </div>
          <div class="panel" :style="{ transform: `translateY(${panel2Parallax}px)` }">
            <img class="panel-img" src="../assets/whatsGoingDown/whatsGoingDownPanel2.png" alt="Image 2">
            <div class="panel-content">
                <h1 class="panel-heading">No coding involved.</h1>
                <p class="panel-text">Ideation and UI/UX design on Figma only!</p>
            </div>
          </div>
          <div class="panel" :style="{ transform: `translateY(${panel3Parallax}px)` }">
            <img class="panel-img" src="../assets/whatsGoingDown/whatsGoingDownPanel3.png" alt="Image 3">
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
    if (window.innerWidth >= 1200) {
      return {
        panel1Parallax: 100,
        panel2Parallax: 900,
        panel3Parallax: 1700,
        prevScrollDirection: 0
      };
    }
    if (window.innerWidth >= 768) {
      return {
        panel1Parallax: 0,
        panel2Parallax: 800,
        panel3Parallax: 1600,
        prevScrollDirection: 0
      };
    }
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
        if (window.innerWidth >= 1200) {
          this.panel1Parallax += scrollDiff * -0.12 * scrollDirection;
          this.panel2Parallax += scrollDiff * 0.08 * scrollDirection;
          this.panel3Parallax += scrollDiff * 0.28 * scrollDirection;
        }
        else if (window.innerWidth >= 768) {
          this.panel1Parallax += scrollDiff * -0.12 * scrollDirection;
          this.panel2Parallax += scrollDiff * 0.11 * scrollDirection;
          this.panel3Parallax += scrollDiff * 0.34 * scrollDirection;
        }
    },
  },
  beforeDestroy() {
    window.removeEventListener('wheel', this.Parallax);
  }
}

</script>

<style scoped>
  .whats-going-down-section {
  display: flex;
  text-align: center;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 2em 1em;
  text-size-adjust: 100%;
  margin-top: 100px;
  overflow: visible;
  margin-bottom: 400px;
  padding: 103px 40px 197px 40px;
}
 .whats-going-down-title {
    color: #09702C;
    text-align: center;
    font-size: 11rem;
    font-style: normal;
    font-weight: 500;
    line-height: 11rem; /* 100% */
    letter-spacing: -0.5625rem;
    text-transform: uppercase;
    text-size-adjust: 100%;
  }
  .whats-going-down-intro {
    display: inline-flex;
    flex-direction: column;
    align-items: center;
    gap: 1.8125rem;
    margin: 0 1px;
  }
  
  .whats-going-down-divider {
    margin-bottom: 30px;
  }
  .whats-going-down-subheading {
    color: #09702C;
    font-size: 30px;
    font-style: normal;
    font-weight: 400;
    line-height: 40px;
    letter-spacing: -1.5px;
    /* margin-bottom: 447px; */
    margin-bottom: -350px;
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
    z-index: 1;
    transition: transform 0.05s;
  }

  .row {
    display: flex;
    flex-direction: row;
    justify-content:space-between;
    gap: 60px;
    height: 150vh;
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

  @media screen and (max-width: 1350px) {
    .whats-going-down-title {
      font-size: 150px;
    }
  }

  @media screen and (max-width: 1200px) {
    .whats-going-down-title {
      font-size: 100px;
      letter-spacing: -4.5px;
      margin: 0 50px;
    }
    .whats-going-down-subheading {
      font-size: 28px;
      margin-bottom: -200px
    }
    .panel-heading {
      font-size: 60px;
      letter-spacing: -4.5px;
      line-height: 68px;
    }
    .panel-text {
      font-size: 24px;
    }
  }

  @media screen and (max-width: 900px) {
    .row {
      gap: 30px;
    }
    .panel-heading {
      font-size: 50px;
      letter-spacing: -4.5px;
      line-height: 68px;
    }
    .panel-text {
      font-size: 22px;
    }
  }

  @media (max-width: 768px) {
    .whats-going-down-title {
      margin: 0 40px;
      line-height: 8rem;
    }
    .row {
      flex-direction: column;
      height: auto;
      gap: 100px;
      align-items: center;
      margin-bottom: 100px;
    }
    .panel {
      width: 75vw;
    }

    .panel-heading {
      font-size: 70px;
      letter-spacing: -4.5px;
      line-height: 68px;
    }
    .panel-text {
      font-size: 30px;
    }
  }

  @media screen and (max-width: 700px) {
  .whats-going-down-title{
    font-size: 80px;
    letter-spacing: -3px;
    line-height: 100px;
  }
  .whats-going-down-divider {
    width: 50px;
    height: 50px;
  }
  .whats-going-down-subheading {
    font-size: 24px;
  }

  .panel {
      width: 65vw;
    }

  .panel-heading {
      font-size: 50px;
      letter-spacing: -4.5px;
      line-height: 60px;
    }
    .panel-text {
      font-size: 24px;
    }
}

@media screen and (max-width: 400px) {
  .whats-going-down-title {
    font-size: 60px;
    line-height: 60px;
    letter-spacing: -2.5px;
  }
  .whats-going-down-subheading {
    font-size: 20px;
    line-height: 28px;
  }

  .whats-going-down-divider {
    width: 40px;
    height: 40px;
  }

  .panel-heading {
    font-size: 40px;
    letter-spacing: -2px;
  }

}

@media screen and (max-width: 300px) {
  .whats-going-down-section {
    margin-top: 50px;
  }

  .row {
    gap: 50px;
  }
  .whats-going-down-title {
    font-size: 40px;
    line-height: 60px;
    letter-spacing: -2px;
  }
  .whats-going-down-subheading {
    font-size: 18px;
  }
  .whats-going-down-divider {
    width: 30px;
    height: 30px;
  }

  .panel-heading {
    font-size: 35px;
    letter-spacing: -2px;
    line-height: 40px;
  }
  .panel-text {
    font-size: 20px;
  }
  
}
</style>
  