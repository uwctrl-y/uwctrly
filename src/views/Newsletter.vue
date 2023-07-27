<template>
  <section>
    <div class="newsletter-section">
      <div class="newsletter-info">
          <p class="newsletter-section-number">0.5</p>
          <h1 class="newsletter-section-heading">stay updated</h1>
          <svg class="newsletter-section-divider" width="71" height="71" viewBox="0 0 71 71" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M35.5001 71C40.8306 71 44 67.1485 44 62.97C44 59.4353 38.5995 46.306 36.4079 41.1235C36.0663 40.3157 34.942 40.3191 34.6048 41.1288C32.4213 46.3714 27 59.7157 27 62.97C27 67.1485 30.1695 71 35.5001 71Z" fill="#E4E4D0"/>
              <path d="M4.25011 53.3613C6.9154 57.9777 11.8356 58.7967 15.4542 56.7075C18.5154 54.9401 27.1855 43.6984 30.5778 39.2092C31.1066 38.5094 30.5415 37.5375 29.6717 37.6503C24.0397 38.3807 9.77253 40.3579 6.95423 41.985C3.33556 44.0743 1.58482 48.7449 4.25011 53.3613Z" fill="#E4E4D0"/>
              <path d="M4.25011 17.3614C6.9154 12.745 11.8356 11.926 15.4542 14.0152C18.5154 15.7825 27.1855 27.0242 30.5778 31.5134C31.1066 32.2132 30.5415 33.1851 29.6717 33.0723C24.0397 32.342 9.77253 30.3648 6.95423 28.7376C3.33556 26.6484 1.58482 21.9778 4.25011 17.3614Z" fill="#E4E4D0"/>
              <path d="M35.4999 6.89956e-07C30.1694 1.12264e-06 27 3.85152 27 8.02996C27 11.5647 32.4005 24.694 34.5921 29.8765C34.9337 30.6843 36.058 30.6809 36.3952 29.8712C38.5787 24.6286 44 11.2843 44 8.02996C44 3.85149 40.8305 2.5727e-07 35.4999 6.89956e-07Z" fill="#E4E4D0"/>
              <path d="M66.7499 17.6387C64.0846 13.0223 59.1644 12.2033 55.5458 14.2925C52.4846 16.0599 43.8145 27.3016 40.4222 31.7908C39.8934 32.4906 40.4585 33.4625 41.3283 33.3497C46.9603 32.6193 61.2275 30.6421 64.0458 29.015C67.6644 26.9257 69.4152 22.2551 66.7499 17.6387Z" fill="#E4E4D0"/>
              <path d="M66.7499 53.6386C64.0846 58.255 59.1644 59.074 55.5458 56.9848C52.4846 55.2174 43.8145 43.9758 40.4222 39.4866C39.8934 38.7868 40.4585 37.8149 41.3283 37.9277C46.9603 38.658 61.2275 40.6352 64.0458 42.2624C67.6644 44.3516 69.4152 49.0222 66.7499 53.6386Z" fill="#E4E4D0"/>
          </svg>
          <p class="newsletter-section-subheading">We'll update you when registration begins</p>
      </div>  
      <form class="newsletter-form">
          <input class="newsletter-email-input" 
              type="email" 
              v-model="email"
              name="email"
              placeholder="Enter your email."
          >
          <input v-on:click="submit" class="newsletter-email-submit" type="submit" value="join our newsletter">
      </form> 
      <div class="newsletter-section-socials">
      <a href="https://www.instagram.com/" target="_blank" class="social-link">
        <img src="../assets/instagramIcon.svg" alt="Instagram">
      </a>
      <a href="https://www.linkedin.com/" target="_blank" class="social-link">
        <img src="../assets/linkedinIcon.svg" alt="LinkedIn">
      </a>
      <a href="" target="_blank" class="social-link">
        <img src="../assets/mailIcon.svg" alt="Email">
      </a>
    </div>  
    </div>
  </section>
</template>

<script>
// import db from '../firestoreInit'
export default {
  // data: function() {
  //   return {
  //     emailAddress: '',
  //   }
  // },
  // methods: {
  //   submit: function() {
  //     db.collection("EmailAddresses").add({
  //       emailAddress: this.emailAddress
  //     })
  //   }
  // }
}
</script>

<style scoped>
.newsletter-section {
  padding: 106px 18rem;
  justify-content: center;
  /* flex-shrink: 1; */
  border-radius: 12px;
  background: #09702C;
}
.newsletter-info {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.8125rem;
  margin-bottom: 8.75rem;
}

.newsletter-section-number {
  color: #E4E4D0;
  /* font-family: Roboto; */
  font-size: 1.25rem;
  font-style: normal;
  font-weight: 500;
  line-height: 1.875rem; /* 150% */
  letter-spacing: -0.0625rem;
}
.newsletter-section-heading {
  color: #E4E4D0;
  text-align: center;
  /* font-family: Roboto; */
  font-size: 11.25rem;
  font-style: normal;
  font-weight: 500;
  line-height: 11.25rem; /* 100% */
  letter-spacing: -0.5625rem;
  text-transform: uppercase;
}

.newsletter-section-divider {
  width: 4.4375rem;
  height: 4.4375rem;
}

.newsletter-section-subheading {
  color: #E4E4D0;
  /* font-family: Roboto; */
  font-size: 1.875rem;
  font-style: normal;
  font-weight: 400;
  line-height: 2.5rem; /* 133.333% */
  letter-spacing: -0.09375rem;
}

.newsletter-form {
  display: inline-flex;
  flex-direction: row;
  align-self: center;
  width: 100%;
}
.newsletter-email-input {
  border-style: none;
  display: flex;
  padding: 1rem;
  align-items: center;
  flex: 2;
  border-radius: 0.3125rem;
  border-radius: 5px;
  background: #09702C;
  color: #E4E4D0;
  border: 4px solid rgba(228, 228, 208, 0.50);
  /* font-family: Roboto; */
  font-size: 2.5rem;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
  letter-spacing: -0.125rem;
  z-index: 1;
}

.newsletter-email-submit {
  border-style: none;;
  display: flex;
  padding: 1rem;
  flex: 1;
  align-items: center;
  justify-content: center;
  gap: 0.625rem;
  border-radius: 0.3125rem;
  background: #E4E4D0;
  color: #09702C;
  /* font-family: Roboto; */
  font-size: 2.5rem;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
  letter-spacing: -0.125rem;
  z-index: 1;
  margin-left: 1rem;
}

.newsletter-section-socials {
  margin-top: 80px;
  display: flex;
  justify-content: center; /* Center the social media links horizontally */
  gap: 32px; /* Adjust the spacing between the logos */
  
}

.social-link {
  display: block; /* Make the entire logo clickable */
  width: 40px; /* Adjust the width of the logos as needed */
  height: 40px; /* Adjust the height of the logos as needed */
  z-index: 1;
}

</style>