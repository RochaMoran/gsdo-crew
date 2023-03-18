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
              ><img src="https://i.postimg.cc/YCV2QBJg/github.png" alt="github"
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
              ><img src="https://i.postimg.cc/NjLfyjPB/email.png" alt="email"
              class="social-media__icon"
            /></a>
          </div>
        </div>
      </div>
      <div class="contact-form-wrapper">
        <form autocomplete="off">
          <div class="form-item">
            <input type="text" name="sender" required />
            <label>Name:</label>
          </div>
          <div class="form-item">
            <input type="text" name="email" required />
            <label>Email:</label>
          </div>
          <div class="form-item">
            <textarea class="" name="message" required></textarea>
            <label>Message:</label>
          </div>
          <button class="submit-btn">Send</button>
        </form>
      </div>
    </div>
  </article>
</template>

<script>
export default {
  name: "ContactForm",
  mounted() {
    const options = {
      rootMargin: '300px',
      threshold: 1.0
    };
    
    const observer = new IntersectionObserver((entries, observer) => {
      entries.forEach(entry => {
        if (entry.intersectionRatio === 1) {
          this.$el.querySelector('.contact-form-wrapper').classList.add('show-wrapper')
          this.$el.querySelector('.contact-links').classList.add('show-links')
          this.$el.querySelector('.contact-box').classList.add('show-item');
          observer.unobserve(entry.target);
        }
      });
    }, options);

    
    observer.observe(this.$el);
  },
};
</script>
