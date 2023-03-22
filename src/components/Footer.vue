<template>
  <footer class="footer-distributed">
    <div class="footer-left">
      <h3>
        GSDO/Crew<span
          ></span>
      </h3>

      <p class="footer-links">
        <a href="#crew" class="link-1">Crew</a>

        <a href="#works">Works</a>

        <a href="#contact">Contact</a>

        <a href="#clients">Clients</a>
      </p>

      <p class="footer-company-name">Copyrights © {{ currentYear }}</p>
    </div>

    <div class="footer-center">
      <!-- <div>
        <i class="fa fa-map-marker"></i>
        <p><span>444 S. Cedros Ave</span> Solana Beach, California</p>
      </div> -->

      <div>
        <i class="fa fa-phone"></i>
        <p>+1.555.555.5555</p>
      </div>

      <div>
        <i class="fa fa-envelope"></i>
        <p><a href="mailto:support@company.com">support@company.com</a></p>
      </div>
    </div>

    <div class="footer-right">
      <p style="color: white" class="footer-company-about">
        <span>About us</span>
        Bringing your ideas to life with seamless design and flawless functionality..
      </p>

      <div class="footer-icons">
        <a href="#"><i class="fa fa-facebook"></i></a>
        <a href="#"><i class="fa fa-twitter"></i></a>
        <a href="#"><i class="fa fa-linkedin"></i></a>
        <a href="#"><i class="fa fa-github"></i></a>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "FooterComponent",
  data() {
    return {
      currentYear: new Date().getFullYear(),
    }
  }
};
</script>
