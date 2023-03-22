<template>
  <article class="section contact" id="contact">
    <div class="contact-box">
      <div class="contact-links">
        <h2 class="contact-title">Contact Us</h2>
        <div class="links">
          <div class="link">
            <a
              ><img
                src="https://i.postimg.cc/m2mg2Hjm/linkedin.png"
                alt="linkedin"
                class="social-media__icon"
            /></a>
          </div>
          <div class="link">
            <a
              ><img
                src="https://i.postimg.cc/YCV2QBJg/github.png"
                alt="github"
                class="social-media__icon"
            /></a>
          </div>
          <div class="link">
            <a
              ><img
                src="https://i.postimg.cc/W4Znvrry/codepen.png"
                alt="codepen"
                class="social-media__icon"
            /></a>
          </div>
          <div class="link">
            <a
              ><img
                src="https://i.postimg.cc/NjLfyjPB/email.png"
                alt="email"
                class="social-media__icon"
            /></a>
          </div>
        </div>
      </div>
      <div class="contact-form-wrapper">
        <form ref="form" autocomplete="off" @submit.prevent="onSubmit()">
          <div class="form-item">
            <input type="text" name="sender" v-model="to_name" :class="{ 'is-invalid': nameError }"/>
            <label for="to_name" :class="{ 'is-invalid__label': nameError }">Name:</label>
            <div v-if="nameError" class="invalid-feedback">{{ nameError }}</div>
          </div>
          <div class="form-item">
            <input type="text" name="to_email" v-model="to_email" :class="{ 'is-invalid': emailError }" />
            <label for="to_email" :class="{ 'is-invalid__label': emailError }">Email:</label>
            <div v-if="emailError" class="invalid-feedback">{{ emailError }}</div>
          </div>
          <div class="form-item">
            <textarea class="" name="message" v-model="message" :class="{ 'is-invalid': messageError }"></textarea>
            <label for="message" :class="{ 'is-invalid__label': messageError }">Message:</label>
            <div v-if="messageError" class="invalid-feedback">{{ messageError }}</div>
          </div>
          <button class="submit-btn">Enviar Mensaje</button>
        </form>
      </div>
    </div>
    <div class="resp-message" v-if="formSubmitted" :class="{'resp-success': resp.ok, 'resp-error': !resp.ok}">{{ resp.message }}</div>
  </article>
</template>

<script>
import emailjs from '@emailjs/browser';

export default {
  name: "ContactForm",
  data() {
    return {
      to_name: "",
      to_email: "",
      message: "",
      nameError: "",
      emailError: "",
      messageError: "",
      formValid: false,
      formSubmitted: false,
      resp: {
        ok: true,
        message: "",
      }
    };
  },
  methods: {
    onSubmit() {
      this.validateForm();
      if (this.formValid) {
        const service_email = {
          email_template: "template_exyu8jo",
          email_service: "service_twhsok6",
          public_key: "2DNfw3vDBqz2tkMEO",
        };

        this.formSubmitted = true;
        emailjs.sendForm(service_email.email_service, service_email.email_template, this.$refs.form, service_email.public_key)
        .then((result) => {
            this.$refs.form.reset();
            this.to_name = "";
            this.to_email = "";
            this.message = "";
            this.formValid = false;
            this.resp = {
              ok: true,
              message: `Message sent successfully! ${result.text}`
            };
        }, (error) => {
            this.resp = {
              ok: false,
              message: `Message not sent! ${error.text}`
            };
        });

        setTimeout(() => {
          this.formSubmitted = false;
        }, 10000);
      }
    },
    validateForm() {
      this.formValid = true;
      this.nameError = "";
      this.emailError = "";
      this.messageError = "";

      if (this.to_name === "") {
        this.nameError = "Whoops! It looks like you forgot to add your name";
        this.formValid = false;
      }

      if (this.to_email === "") {
        this.emailError = "Whoops! It looks like you forgot to add your email";
        this.formValid = false;
      } else if (!this.isValidEmail(this.to_email)) {
        this.emailError = "Whoops! It looks like you added an invalid email";
        this.formValid = false;
      }

      if (this.message === "") {
        this.messageError = "Whoops! It looks like you forgot to add a message";
        this.formValid = false;
      }
    },
    isValidEmail(email) {
      const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      return re.test(email);
    },
  },
  mounted() {
    const options = {
      rootMargin: "300px",
      threshold: 1.0,
    };

    const observer = new IntersectionObserver((entries, observer) => {
      entries.forEach((entry) => {
        if (entry.intersectionRatio === 1) {
          this.$el
            .querySelector(".contact-form-wrapper")
            .classList.add("show-wrapper");
          this.$el.querySelector(".contact-links").classList.add("show-links");
          this.$el.querySelector(".contact-box").classList.add("show-item");
          observer.unobserve(entry.target);
        }
      });
    }, options);

    observer.observe(this.$el);
  },
};
</script>
