<template>
  <section class="section crew" id="crew">
    <h3 class="works-title">Crew</h3>
    <div class="crew-container">
      <div class="crew-container-carrousel">
        <CrewMember
          v-for="(member, i) in members"
          :key="member.id"
          :member="member"
          :isActive="currentIndex === (i - 1)"
        ></CrewMember>
      </div>
    </div>
    <div class="crew-controls">
      <button class="button-prev" @click="prevSlide()">
        <img src="@/assets/images/next.png" alt="next">
      </button>
      <button class="button-next" @click="nextSlide()">
        <img src="@/assets/images/next.png" alt="back"></button>
    </div>
  </section>
</template>

<script>
import CrewMember from "./MemberCrew.vue";
import stevenImg from "@/assets/images/me.png";

export default {
  name: "CrewComponent",
  components: {
    CrewMember,
  },
  data() {
    return {
      currentIndex: 0,
      interval: null,
      scrollPos: 0,
      members: [
        {
          id: 1,
          name: "Steven Edgardo Rocha Moran",
          rol: "Desarrollador Web - Frontend",
          image: stevenImg,
        },
        {
          id: 2,
          name: "##### ###### ##### ######",
          rol: "##### ###### ##### ###### ######",
          image: stevenImg,
        },
        {
          id: 3,
          name: "##### ###### ##### ######",
          rol: "##### ###### ##### ###### ######",
          image: stevenImg,
        },
        {
          id: 4,
          name: "##### ###### ##### ######",
          rol: "##### ###### ##### ###### ######",
          image: stevenImg,
        },
        {
          id: 5,
          name: "##### ###### ##### ######",
          rol: "##### ###### ##### ###### ######",
          image: stevenImg,
        },
        {
          id: 6,
          name: "##### ###### ##### ######",
          rol: "##### ###### ##### ###### ######",
          image: stevenImg,
        },
        {
          id: 7,
          name: "Ultimo ###### ##### ######",
          rol: "##### ###### ##### ###### ######",
          image: stevenImg,
        },
      ],
    };
  },
  methods: {
    prevSlide() {
      if (this.scrollPos > 0) {
        const carrousel = document.querySelector(".crew-container-carrousel");
        this.currentIndex -= 1;
        console.log(window.innerWidth);
        this.scrollPos -= window.innerWidth < 600 ? 325 : 400;
        carrousel.scrollTo({
          top: 0,
          left: this.scrollPos,
          behavior: "smooth"
        });
      }
    },
    nextSlide() {
      const carrousel = document.querySelector(".crew-container-carrousel");
      if (this.scrollPos + carrousel.clientWidth < carrousel.scrollWidth) {
        this.currentIndex += 1;
        this.scrollPos += window.innerWidth < 600 ? 325 : 400;
        carrousel.scrollTo({
          top: 0,
          left: this.scrollPos,
          behavior: "smooth"
        });
      }
    },
  },
  mounted() {
    const options = {
      rootMargin: "20px",
      threshold: 1.0,
    };

    const observer = new IntersectionObserver((entries, observer) => {
      entries.forEach((entry) => {
        if (entry.intersectionRatio === 1) {
          entry.target.classList.add("show-item");
          observer.unobserve(entry.target);
        }
      });
    }, options);

    observer.observe(this.$el);
  },
};
</script>
