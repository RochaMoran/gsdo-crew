<template>
  <footer>
    <section class="footer-distributed">
      <article class="footer-left">
        <h3>/Get to know us<span></span></h3>
  
        <p class="footer-links">
          Unleash your brand's potential with our creative crew's cutting-edge
          solutions and innovative strategies, tailored to elevate your online and
          offline presence and captivate your target audience.
        </p>
      </article>
      <article class="footer-center">
        <div>
          <p><span>New Jersey</span> 491 Elm Ave, 2nd Floor bogota Nj07603</p>
          <br>
          <p>/Social Media</p>
          <ul class="social-media-footer">
            <li>
              <a href="#">
                <img src="@/assets/icons/facebook-icon.svg" alt="facebook">
              </a>
            </li>
            <li>
              <a href="#">
                <img src="@/assets/icons/twiter-icon.svg" alt="facebook">
              </a>
            </li>
            <li>
              <a href="#">
                <img src="@/assets/icons/linkedin-icon.svg" alt="facebook">
              </a>
            </li>
            <li>
              <a href="#">
                <img src="@/assets/icons/instagram-icon.svg" alt="facebook">
              </a>
            </li>
            <li>
              <a href="#">
                <img src="@/assets/icons/youtube-icon.svg" alt="facebook">
              </a>
            </li>
          </ul>
        </div>
  
        <div>
          <p><span>Florida</span>14199 Wake Robin Drive Brooksville FL 34604</p>
          <p>551.775.0020</p>
          <br>
          <br>
          <p>Work /Crew /Clients /Home</p>
        </div>
      </article>
  
      <article class="footer-right">
       <ContactForm />
      </article>
    </section>
     <section className='main-footer__bottom'>
        <article className='main-footer__paragraph main-footer__firstParagraph'>
          <a href='privacy.html'>
            PRIVACY POLITY | TERMS OF USE | NOTICE OF NONDISCRIMINATION |
          </a>
          Site Developed by <span className='footer-span__resalt'>GSDO/Crew</span>
        </article>
        <article className='main-footer__paragraph main-footer__lastParagraph'>
          Copyrights © {{ currentYear }} GSDO/Crew, All rights reserved.
        </article>
      </section>
  </footer>
</template>

<script>
import ContactForm from "./ContactForm.vue";

export default {
  name: "FooterComponent",
  components: {
    ContactForm,
  },
  data() {
    return {
      currentYear: new Date().getFullYear(),
    };
  },
};
</script>
