<template>
  <section>
    <div class="registration-section">
      <div class="registration-info">
          <h1 class="registration-section-heading">register now</h1>
          <svg class="registration-section-divider" width="71" height="71" viewBox="0 0 71 71" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M35.5001 71C40.8306 71 44 67.1485 44 62.97C44 59.4353 38.5995 46.306 36.4079 41.1235C36.0663 40.3157 34.942 40.3191 34.6048 41.1288C32.4213 46.3714 27 59.7157 27 62.97C27 67.1485 30.1695 71 35.5001 71Z" fill="#E4E4D0"/>
              <path d="M4.25011 53.3613C6.9154 57.9777 11.8356 58.7967 15.4542 56.7075C18.5154 54.9401 27.1855 43.6984 30.5778 39.2092C31.1066 38.5094 30.5415 37.5375 29.6717 37.6503C24.0397 38.3807 9.77253 40.3579 6.95423 41.985C3.33556 44.0743 1.58482 48.7449 4.25011 53.3613Z" fill="#E4E4D0"/>
              <path d="M4.25011 17.3614C6.9154 12.745 11.8356 11.926 15.4542 14.0152C18.5154 15.7825 27.1855 27.0242 30.5778 31.5134C31.1066 32.2132 30.5415 33.1851 29.6717 33.0723C24.0397 32.342 9.77253 30.3648 6.95423 28.7376C3.33556 26.6484 1.58482 21.9778 4.25011 17.3614Z" fill="#E4E4D0"/>
              <path d="M35.4999 6.89956e-07C30.1694 1.12264e-06 27 3.85152 27 8.02996C27 11.5647 32.4005 24.694 34.5921 29.8765C34.9337 30.6843 36.058 30.6809 36.3952 29.8712C38.5787 24.6286 44 11.2843 44 8.02996C44 3.85149 40.8305 2.5727e-07 35.4999 6.89956e-07Z" fill="#E4E4D0"/>
              <path d="M66.7499 17.6387C64.0846 13.0223 59.1644 12.2033 55.5458 14.2925C52.4846 16.0599 43.8145 27.3016 40.4222 31.7908C39.8934 32.4906 40.4585 33.4625 41.3283 33.3497C46.9603 32.6193 61.2275 30.6421 64.0458 29.015C67.6644 26.9257 69.4152 22.2551 66.7499 17.6387Z" fill="#E4E4D0"/>
              <path d="M66.7499 53.6386C64.0846 58.255 59.1644 59.074 55.5458 56.9848C52.4846 55.2174 43.8145 43.9758 40.4222 39.4866C39.8934 38.7868 40.4585 37.8149 41.3283 37.9277C46.9603 38.658 61.2275 40.6352 64.0458 42.2624C67.6644 44.3516 69.4152 49.0222 66.7499 53.6386Z" fill="#E4E4D0"/>
          </svg>
          <p class="registration-section-subheading">Select the button below to register</p>
      </div>  
      <div class="registration-button">
        <a href="https://forms.gle/aFEpStEECJ84yo8D8" target="_blank">
          <div class="button-inner">
            <div>register here</div>
            <img ref="graphic" src="../assets/expandArrowGreen.svg"/>
          </div>
        </a>
      </div>
      <div class="registration-section-socials">
      <a href="https://www.instagram.com/ctrl.plus.y/" target="_blank" class="social-link">
        <img src="../assets/registration/instagramIcon.svg" alt="Instagram">
      </a>
      <a href="https://www.linkedin.com/company/ctrl-plus-y/" target="_blank" class="social-link">
        <img src="../assets/registration/linkedinIcon.svg" alt="LinkedIn">
      </a>
      <a href="mailto:ctrlplusy2023@gmail.com" class="social-link">
        <img src="../assets/registration/mailIcon.svg" alt="Email">
      </a>
    </div> 
    </div>
    <footer class="registration-section-footer">
      <img src="../assets/registration/registrationSectionFooterImage.svg" alt="Ctrl+y"> 
    </footer>
  </section>
</template>

<script>
export default {
}
</script>

<style scoped>
.registration-section {
  padding: 106px 18rem;
  justify-content: center;
  border-top-right-radius: 16px;
  border-top-left-radius: 16px;
  background: #09702C;
  overflow: hidden;
  margin-bottom: -2px;
}
.registration-info {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.8125rem;
  margin-bottom: 8.75rem;
  margin-right: -30%;
  margin-left: -30%;
}

.registration-section-heading {
  color: #E4E4D0;
  text-align: center;
  font-size: 11.25rem;
  font-style: normal;
  font-weight: 500;
  line-height: 11.25rem; /* 100% */
  letter-spacing: -0.5625rem;
  text-transform: uppercase;
}

.registration-section-divider {
  width: 4.4375rem;
  height: 4.4375rem;
}

.registration-section-subheading {
  color: #E4E4D0;
  font-size: 1.875rem;
  font-style: normal;
  font-weight: 400;
  line-height: 2.5rem; /* 133.333% */
  letter-spacing: -0.09375rem;
  text-align: center;
  margin-bottom: -50px;
}
.registration-button {
  width: 40%;
  font-size: 40px;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
  letter-spacing: -2px;
  margin: auto;
}
.button-inner {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex: 1 0 0;
  border-radius: 5px;
  height: 80px;
  padding: 16px 24px;
  border-radius: 0.3125rem;
  background: #E4E4D0;
  color: #09702C;
  margin-bottom: 16px;
}
/* .register-button {
  border-style: none;
  display: flex;
  padding: 1rem;
  flex: 1;
  align-items: center;
  justify-content: center;
  border-radius: 0.3125rem;
  background: #E4E4D0;
  color: #09702C;
  font-size: 2.3rem;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
  letter-spacing: -0.125rem;
}

.register-button:hover {
  border-style: none;
  display: flex;
  padding: 1rem;
  flex: 1;
  align-items: center;
  justify-content: center;
  border-radius: 0.3125rem;
  background: #E4E4D0;
  color: #09702C;
  font-size: 2.3rem;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
  letter-spacing: -0.125rem;
  z-index: 1;
} */

.registration-section-socials {
  margin-top: 80px;
  display: flex;
  justify-content: center; 
  gap: 32px;
  
}

.social-link {
  display: block;
  z-index: 1;
}

a:hover {
  background-color: transparent;
}

.registration-section-footer {
  display: flex;
  background: #09702C;
  justify-content: flex-end;
  align-items: flex-end;
  height: 110%;
  margin-top: auto;
}

.registration-section-footer img {
    max-width: 100%;
  }

@media screen and (max-width: 1350px) {
  .registration-section {
    padding-right: 0;
    padding-left: 0;
  }
  .registration-section-heading {
    font-size: 150px;
  }
  .registration-button {
    font-size: 34px;
  }
}

@media screen and (max-width: 1200px) {
  .registration-section-heading {
    font-size: 100px;
    letter-spacing: -4.5px;
  }
  .registration-section-subheading {
    font-size: 24px;
  }
  .registration-button {
    font-size: 30px;
  }
}

@media screen and (max-width: 800px) {
  .registration-section-heading {
    font-size: 80px;
    letter-spacing: -4.5px;
    line-height: 110px;
  }

  .registration-section-subheading {
    margin-bottom: -40px;
  }

  .registration-section-divider {
    width: 60px;
    height: 60px;
  }
  .registration-button {
    font-size: 28px;
    padding: 0.8rem;
  }
  .button-inner > img {
  height: 20px;
}
}

@media screen and (max-width: 700px) {
  .registration-section {
    margin-bottom: -80px;
  }
  .registration-section-heading {
    margin: 0 200px;
  }

  .registration-button {
    width: 50%;
  }

  .social-link img {
    width: 40px;
    height: 40px;
  }

  
}
@media screen and (max-width: 500px) {
  .registration-section {
    margin-bottom: -100px;
  }
  .registration-section-subheading {
    margin: 0 200px -40px 200px;
  }

  .registration-section-divider {
    width: 50px;
    height: 50px;
  }
  .registration-button {
    width: 70%;
  }
  .social-link img {
    width: 35px;
    height: 35px;
  }

}

@media screen and (max-width: 400px) {
  .registration-section-heading {
    font-size: 60px;
    line-height: 60px;
    letter-spacing: -2.5px;
  }
  .registration-section-subheading {
    font-size: 20px;
    line-height: 28px;
    margin: 0 150px -50px 150px;
  }

  .registration-section-divider {
    width: 40px;
    height: 40px;
  }
  .registration-button {
    font-size: 24px;
  }

  .button-inner > img {
  height: 15px;
}
}

@media screen and (max-width: 300px) {
  .registration-section {
    margin-bottom: -130px;
  }
  .registration-section-heading {
    font-size: 40px;
    line-height: 60px;
    letter-spacing: -2px;
  }
  .registration-section-subheading {
    font-size: 18px;
  }
  .registration-section-divider {
    width: 30px;
    height: 30px;
  }
  .registration-button {
    font-size: 20px;
  }

  .button-inner > img {
  height: 12px;
}

  .social-link img {
    width: 30px;
    height: 30px;
  }
}
</style>