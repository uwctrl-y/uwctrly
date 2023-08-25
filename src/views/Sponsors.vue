<template>
  <section class="sponsors-section">

    <div class="title-section">
      <div class="title">SUPPORT US</div>
      <div class="subtitle">(please)</div>
    </div>

    <div class="join-sponsor">
      <div class="heading">Join CTRL + y as a <i>sponsor</i>.</div>
      <div class="buttons">
        <a :href="pdfUrl" target="_blank" rel="noopener noreferrer">
          <div class="button-top">
            <div>see sponsorship package</div>
            <img ref="graphic" src="../assets/expandArrow.svg" />
          </div>
        </a>
        <a href="mailto:ctrlplusy2023@gmail.com">
        <div class="button-bottom">
          <div>contact us</div>
          <img ref="graphic" src="../assets/expandArrowGreen.svg" />
        </div>
      </a>
      </div>
      <div class="subheading">Help us provide an invaluable experience to aspiring designers by joining us as a
        sponsor. Support their
        journey and leave a lasting impression through CTRL + y!</div>
    </div>

    <div class="sponsor-box-one">
      <img ref="graphic" src="../assets/sponsorLogoExample1.svg" />
      <div>
        <div class="sponsor-name-one">Your name could be here.</div>
        <div class="sponsor-desc-one"> And your logo could be in the card <span v-if="windowWidth < 800">above</span><span
            v-else>to the left</span>! Check out our sponsorship package
          or email us for more information.</div>
        <div class="sponsor-button-one">Your website could be linked here!</div>
      </div>
    </div>

    <div class="sponsor-box-two">
      <img ref="graphic" src="../assets/sponsorLogoExample2.svg" />
      <div class="sponsor-name-two">Or here, with our mascot Yee!</div>
    </div>

  </section>
</template>

<script>
import pdf from "../assets/externalFiles/CorporatePackage.pdf";
export default {
  data() {
    return {
      windowWidth: window.innerWidth,
      pdfUrl: pdf
    }
  },

  mounted() {
    this.$nextTick(() => {
      window.addEventListener('resize', this.onResize);
    })
  },

  beforeDestroy() {
    window.removeEventListener('resize', this.onResize);
  },

  methods: {
    onResize() {
      this.windowWidth = window.innerWidth
    }
  }

}
</script>

<style scoped>
.sponsors-section {
  border-radius: 16px;
  background: #E4E4D0;
  padding: 96px 47px 113px 47px;
  color: #09702C;
}

.title-section {
  display: flex;
  justify-content: center;
  margin-bottom: 295px;
}

.title {
  font-size: 180px;
  font-style: normal;
  font-weight: 500;
  line-height: 180px;
  letter-spacing: -9px;
  text-transform: uppercase;
}

.subtitle {
  font-size: 30px;
  font-style: italic;
  font-weight: 500;
  line-height: 30px;
  letter-spacing: -1.5px;
  margin-left: 20px;
}

.join-sponsor {
  display: flex;
  justify-content: space-between;
  margin-bottom: 163px;
}

.heading {
  font-size: 84px;
  font-style: normal;
  font-weight: 500;
  line-height: 1.1em;
  letter-spacing: -4.2px;
  width: 30%;
}

.heading>i {
  font-size: 84px;
  font-style: italic;
  font-weight: 500;
  line-height: 1.1em;
  letter-spacing: -4.2px;
}

.buttons {
  width: 35%;
  font-size: 40px;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
  letter-spacing: -2px;
}

.button-top,
.button-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex: 1 0 0;
  border-radius: 5px;
  height: 80px;
  padding: 16px 24px;
}

a {
  color: #09702C
}

.button-top {
  border: 2px solid #09702C;
  background: #09702C;
  color: #F0F0EC;
  margin-bottom: 16px;
}

.button-bottom {
  border: 2px solid rgba(9, 112, 44, 0.25);
  background: rgba(9, 112, 44, 0.25);
}

.subheading {
  font-size: 30px;
  font-style: normal;
  font-weight: 400;
  line-height: 40px;
  letter-spacing: -1.5px;
  width: 25%;
}

.sponsor-box-one {
  display: flex;
  background-color: #09702C;
  border-radius: 12px;
}

.sponsor-box-one>img {
  width: 50%;
}

.sponsor-box-one> :nth-child(2) {
  border-radius: 0px 12px 12px 0px;
  border: 4px solid #09702C;
  background: #F0F0EC;
  padding: 32px;
  position: relative;
}

.sponsor-name-one {
  font-size: 84px;
  font-style: normal;
  font-weight: 500;
  line-height: 90px;
  letter-spacing: -4.2px;
  margin-bottom: 32px;
}

.sponsor-desc-one {
  font-size: 30px;
  font-style: normal;
  font-weight: 400;
  line-height: 40px;
  letter-spacing: -1.5px;
  text-indent: 35px;
}

.sponsor-button-one {
  font-size: 30px;
  font-style: normal;
  font-weight: 400;
  line-height: 40px;
  letter-spacing: -1.5px;
  border-radius: 5px;
  background: rgba(9, 112, 44, 0.10);
  padding: 16px;
  position: absolute;
  bottom: 32px;
  right: 32px;
}

.sponsor-box-two {
  align-items: center;
  text-align: center;
  width: 100%;
  margin-block: 160px;
}

.sponsor-name-two {
  font-size: 30px;
  font-style: normal;
  font-weight: 400;
  line-height: 40px;
  letter-spacing: -1.5px;
  margin-top: 60px;
}

@media screen and (max-width: 1880px) {
  .buttons {
    width: 30%;
    font-size: 35px;
  }

  .subheading {
    width: 30%;
  }
}

@media screen and (max-width: 1800px) {
  .buttons {
    width: 25%;
    font-size: 30px;
    margin-block: 10px;
  }

  .button-top,
  .button-bottom {
    padding: 10px 18px;
    height: 70px;
  }

  .heading,
  .heading>i {
    font-size: 75px;
  }

}

@media screen and (max-width: 1550px) {
  .buttons {
    font-size: 1.75vw;
  }
  .sponsor-name-one {
    font-size: 60px;
    line-height: 68px;
  }

  .sponsor-desc-one,
  .sponsor-button-one {
    font-size: 24px;
    line-height: 36px;
  }
}

@media screen and (max-width: 1350px) {
  .title-section {
    margin-bottom: 200px;
  }

  .title {
    font-size: 150px;
  }

  .heading,
  .heading>i {
    font-size: 60px;
  }

  .sponsor-box-one> :nth-child(2) {
    padding: 20px;
  }

  .sponsor-name-one {
    font-size: 50px;
    line-height: 56px;
  }

  .sponsor-button-one {
    bottom: 20px;
    right: 20px;
  }
}

@media screen and (max-width: 1200px) {
  .title-section {
    margin-bottom: 150px;
  }

  .title {
    font-size: 100px;
  }

  .buttons {
    width: 30%;
    font-size: 2vw;
    letter-spacing: -1.5px;
  }

  .button-top,
  .button-bottom {
    height: 60px;
  }

  .subheading {
    font-size: 24px;
  }

  .sponsor-box-one>img {
    height: 500px;
  }

  .sponsor-name-one {
    font-size: 40px;
    line-height: 46px;
    letter-spacing: -3.6px;
  }

  .sponsor-button-one {
    font-size: 20px;
    padding: 12px;
  }

}

@media screen and (max-width: 900px) {
  .button-top, .button-bottom {
    padding: 10px;
  }
}

@media screen and (max-width: 800px) {
  .title-section {
    margin-bottom: 100px;
  }

  .title {
    font-size: 80px;
    letter-spacing: -4.5px;
    line-height: 110px;
  }

  .subtitle {
    margin-left: 10px;
  }

  .join-sponsor {
    margin-bottom: 100px;
    display: block;
  }

  .heading,
  .heading>i {
    font-size: 50px;
    width: 100%;
  }

  .buttons {
    width: 100%;
    font-size: 3vw;
    display: flex;
    justify-content: space-between;
  }

  .button-top, .button-bottom {
    width: 40vw;
  }

  .subheading {
    width: 100%;
  }

  .sponsor-box-one {
    display: block;
  }

  .sponsor-box-one>img {
    width: 100%;
    height: 400px;
  }

  .sponsor-box-one> :nth-child(2) {
    border-radius: 0 0 12px 12px;
  }

  .sponsor-desc-one {
    margin-bottom: 150px;
  }
}

@media screen and (max-width: 625px) {
  .title-section {
    margin-bottom: 60px !important;
  }

  .title {
    font-size: 50px;
    line-height: 90px;
  }

  .heading,
  .heading>i {
    font-size: 30px;
    letter-spacing: -2.4px;
  }

  .buttons {
    letter-spacing: -1px;
  }
  .button-top, .button-bottom {
    height: auto;
  }

  .button-top > img,.button-bottom > img {
    height: 15px;
  } 
}


@media screen and (max-width: 700px) {
  .title-section {
    margin-bottom: 80px;
  }

  .title {
    font-size: 60px;
    line-height: 100px;
  }

  .heading,
  .heading>i {
    font-size: 40px;
    letter-spacing: -3.6px;
  }

  .sponsor-desc-one {
    margin-bottom: 80px;
  }

  .sponsor-button-one {
    padding: 10px;
  }

  .sponsor-name-two {
    margin-top: 30px;
  }

}

@media screen and (max-width: 500px) {
  .sponsors-section {
    padding-top: 47px;
  }

  .title-section {
    margin-bottom: 60px;
  }

  .title {
    font-size: 40px;
    line-height: 80px;
  }

  .subtitle {
    font-size: 20px;
  }

  .join-sponsor {
    margin-bottom: 50px;
  }

  .heading,
  .heading>i {
    font-size: 24px;
    letter-spacing: -2px;
  }

  .buttons {
    font-size: 20px;
  }

  .button-top,
  .button-bottom {
    height: 50px;
    padding: 10px;
  }

  .subheading {
    font-size: 18px;
    line-height: 28px;
  }

  .sponsor-box-one>img {
    height: 300px;
  }

  .sponsor-name-one {
    font-size: 28px;
    letter-spacing: -2.5px;
    line-height: 36px;
    margin-bottom: 20px;
  }

  .sponsor-desc-one {
    font-size: 20px;
    line-height: 32px;
    margin-bottom: 30px;
  }

  .sponsor-button-one {
    font-size: 16px;
    line-height: 24px;
    position: relative;
    justify-items: center;
    bottom: auto;
    right: auto;
    text-align: center;
  }

  .sponsor-box-two {
    margin-block: 100px;
  }

  .sponsor-box-two>img {
    height: 125px;
  }

  .sponsor-name-two {
    font-size: 28px;
  }

}

@media screen and (max-width: 450px) {
  .title {
    font-size: 30px;
    line-height: 60px;
    letter-spacing: -2.5px;
  }

  .subtitle {
    font-size: 15px;
    margin-left: 5px;
  }

  .buttons {
    font-size: 15px;
    letter-spacing: -1px;
  }

  .button-top,
  .button-bottom {
    padding: 5px;
    height: 40px;
  }

  .button-top>img,
  .button-bottom>img {
    width: 15px;
  }

  .sponsor-box-one>img {
    height: 200px;
  }

}


@media screen and (max-width: 400px) {
  .button-top, .button-bottom {
    width: 35vw;
  }

  .buttons {
    font-size: 4vw;
  }
}

@media screen and (max-width: 300px) {
  .sponsors-section {
    padding: 20px;
  }

  .title {
    font-size: 25px;
    line-height: 60px;
    letter-spacing: -2px;
  }

  .subtitle {
    display: none;
  }

  .button-top,
  .button-bottom {
    padding: 10px;
    height: 50px;
  }

  .sponsor-box-one>img {
    height: 150px;
  }

}


</style>