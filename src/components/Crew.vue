<template>
  <section class="section crew" id="crew">
    <TitleComponent title="THE CREW" />
    <div class="crew-container">
      <div class="crew-container-carrousel">
        <CrewMember
          v-for="member in members"
          :key="member.id"
          :member="member"
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
import stevenImg from "@/assets/images/me.jpg";
import TitleComponent from "@/components/Title.vue";

export default {
  name: "CrewComponent",
  components: {
    CrewMember,
    TitleComponent
  },
  data() {
    return {
      currentIndex: 0,
      interval: null,
      scrollPos: 0,
      members: [
        {
          id: 1,
          name: "Steven Rocha",
          rol: "Web Developer/UX",
          image: stevenImg,
        },
        {
          id: 2,
          name: "Hans Daniel",
          rol: "Creative Director",
          image: stevenImg,
        },
        {
          id: 3,
          name: "Euclides Alonso",
          rol: "SCD/3D Artist",
          image: stevenImg,
        },
        {
          id: 4,
          name: "Marlene Nuñez",
          rol: "Project Manager",
          image: stevenImg,
        },
        {
          id: 5,
          name: "Nestor Molina",
          rol: "Desarrollador Web",
          image: stevenImg,
        },
        {
          id: 6,
          name: "Nestor Del Prado",
          rol: "Diseñador Gráfico",
          image: stevenImg,
        }
      ],
    };
  },
  methods: {
    prevSlide() {
      if (this.scrollPos > 0) {
        const carrousel = document.querySelector(".crew-container-carrousel");
        this.currentIndex -= 1;
        this.scrollPos -= window.innerWidth < 600 ? 350 : 400;
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
        this.scrollPos += window.innerWidth < 600 ? 350 : 400;
        carrousel.scrollTo({
          top: 0,
          left: this.scrollPos,
          behavior: "smooth"
        });
      }
    },
  }
};
</script>
