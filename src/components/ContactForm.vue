<template>
    <form ref="form" autocomplete="off" @submit.prevent="onSubmit()">
      <div class="form-item">
        <input placeholder="Name" type="text" name="sender" v-model="to_name" :class="{ 'is-invalid': nameError }"/>
        <div v-if="nameError" class="invalid-feedback">{{ nameError }}</div>
      </div>
      <div class="form-item">
        <input placeholder="Email" type="text" name="to_email" v-model="to_email" :class="{ 'is-invalid': emailError }" />
        <div v-if="emailError" class="invalid-feedback">{{ emailError }}</div>
      </div>
      <div class="form-item">
        <div class="form-textarea">
          <textarea rows="1" placeholder="Message" name="message" v-model="message" :class="{ 'is-invalid': messageError }"></textarea>
          <button class="submit-btn">Send</button>
        </div>
        <div v-if="messageError" class="invalid-feedback">{{ messageError }}</div>
      </div>
    </form>
    <div class="resp-message" v-if="formSubmitted" :class="{'resp-success': resp.ok, 'resp-error': !resp.ok}">{{ resp.message }}</div>
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
