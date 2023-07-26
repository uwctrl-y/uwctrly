<template>
  <section class="sponsors-section">

    <div class="title-section">
      <div class="title">SUPPORT US</div>
      <div class="subtitle">(please)</div>
    </div>

    <div class="join-sponsor">
      <div class="heading">Join CTRL + y as a <i>sponsor</i>.</div>
      <div class="buttons">
        <div class="button-top">
          <div>see sponsorship package</div>
          <img class="svg-arrow" ref="graphic" src="../assets/expandArrow.svg" />
        </div>
        <div class="button-bottom">
          <div>contact us</div>
          <img class="svg-arrow" ref="graphic" src="../assets/expandArrowGreen.svg" />
        </div>
      </div>
      <div class="subheading">Help us provide an invaluable experience to aspiring designers by joining us as a
        sponsor. Support their
        journey and leave a lasting impression through CTRL + y!</div>
    </div>

    <div class="sponsor-box-one">
      <img class="svg-arrow" ref="graphic" src="../assets/sponsorLogoExample1.svg" />
      <div>
        <div class="sponsor-name-one">Your name could be here.</div>
        <div class="sponsor-desc-one"> And your logo could be in the card to the left! Check out our sponsorship package
          or email us for more information.</div>
        <div class="sponsor-button-one">Your website could be linked here!</div>
      </div>
    </div>

    <div class="sponsor-box-two">
      <img class="svg-arrow" ref="graphic" src="../assets/sponsorLogoExample2.svg" />
      <div class="sponsor-name-two">Or here, with our mascot Yee!</div>
    </div>

  </section>
</template>

<script>

export default {

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
  /* text-align: center; */
  font-size: 180px;
  font-style: normal;
  font-weight: 500;
  line-height: 180px;
  /* 100% */
  letter-spacing: -9px;
  text-transform: uppercase;
}

.subtitle {
  font-size: 30px;
  font-style: italic;
  font-weight: 500;
  line-height: 30px;
  /* 100% */
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
  line-height: 90px;
  /* 107.143% */
  letter-spacing: -4.2px;
  width: 30%;
}

.heading>i {
  font-size: 84px;
  font-style: italic;
  font-weight: 500;
  line-height: 90px;
  letter-spacing: -4.2px;
}

.buttons {
  width: 35%;
}

.button-top,
.button-bottom {
  font-size: 40px;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
  letter-spacing: -2px;
  display: flex;
  padding: 16px 24px;
  justify-content: space-between;
  align-items: center;
  flex: 1 0 0;
  border-radius: 5px;
}

.button-top {
  border: 4px solid #09702C;
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
  /* 133.333% */
  letter-spacing: -1.5px;
  width: 25%;
}

.sponsor-box-one {
  display: flex;
  background-color: #09702C;
  border-radius: 12px;
}

.sponsor-box-one > :nth-child(2) {
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
  /* 107.143% */
  letter-spacing: -4.2px;
  margin-bottom: 32px;
}

.sponsor-desc-one {
  font-size: 30px;
  font-style: normal;
  font-weight: 400;
  line-height: 40px;
  /* 133.333% */
  letter-spacing: -1.5px;
  text-indent: 35px;
}

.sponsor-button-one {
  font-size: 30px;
  font-style: normal;
  font-weight: 400;
  line-height: 40px;
  /* 133.333% */
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
  /* 133.333% */
  letter-spacing: -1.5px;
  margin-top: 60px;
}
</style>