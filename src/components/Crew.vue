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
import joelImg from "@/assets/images/crew/nestor-del-prado.webp";
import stevenImg from "@/assets/images/crew/steven-rocha.webp";
import albertoImg from "@/assets/images/crew/alberto-molina.webp";
import euclidesImg from "@/assets/images/crew/euclides-alonso.webp";
import hansImg from "@/assets/images/crew/hans-daniel.webp";
import fabricioImg from "@/assets/images/crew/fabricio-placencia.webp";
import marleneImg from "@/assets/images/crew/marlene-nunez.webp";
import oliverImg from "@/assets/images/crew/oliver-hernandez.webp";
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
          name: "Nestor Del Prado",
          rol: "Creative",
          image: joelImg,
        },
        {
          id: 2,
          name: "Hans Daniel",
          rol: "Creative",
          image: hansImg,
        },
        {
          id: 3,
          name: "Euclides Alonso",
          rol: "Creative/3D Artist",
          image: euclidesImg,
        },
        {
          id: 4,
          name: "Marlene Nuñez",
          rol: "Project Coordinator",
          image: marleneImg,
        },
        {
          id: 5,
          name: "Alberto Molina",
          rol: "Web Developer/UX",
          image: albertoImg,
        },
        {
          id: 6,
          name: "Steven Rocha",
          rol: "Web Developer/UX",
          image: stevenImg,
        },
        {
          id: 7,
          name: "Fabricio Placencia",
          rol: "Project Manager",
          image: fabricioImg,
        },
        {
          id: 8,
          name: "Oliver Hernandez",
          rol: "Technology Advisor",
          image: oliverImg,
        },
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
