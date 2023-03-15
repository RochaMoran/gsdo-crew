<template>
  <section class="section crew">
    <h3 class="works-title">Crew</h3>
    <div class="crew-container">
      <div class="crew-container-carrousel" :style="{ transform: 'translateX(' + (-currentIndex * 50) + '%)' }">
        <CrewMember v-for="member in members" :key="member.id" :member="member"></CrewMember>
      </div>
    </div>
    <div class="crew-controls">
      <button @click="prevSlide()">Prev</button>
      <button @click="nextSlide()">Next</button>
    </div>
  </section>
</template>

<script>
import CrewMember from "./MemberCrew.vue";
import stevenImg from "@/assets/images/me.png";

export default {
  name: "CrewComponent",
  components: {
    CrewMember
  },
  data () {
    return {
      currentIndex: 0,
      members: [
        {
          id: 1,
          name: "Steven Edgardo Rocha Moran",
          rol: "Desarrollador Web Full Stack",
          image: stevenImg
        },
        {
          id: 2,
          name: "Nestor Moran",
          rol: "Desarrollador Web Full Stack",
          image: stevenImg
        },
      ]
    }
  },
  created() {
    setInterval(this.nextSlide, 5000);
  },
  methods: {
    prevSlide() {
      this.currentIndex = (this.currentIndex === 0) ? this.members.length - 1 : this.currentIndex - 1;
    },
    nextSlide() {
      this.currentIndex = (this.currentIndex === this.members.length - 1) ? 0 : this.currentIndex + 1;
    }
  }
};
</script>
