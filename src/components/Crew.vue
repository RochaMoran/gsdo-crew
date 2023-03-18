<template>
  <section class="section crew" id="crew">
    <h3 class="works-title">Crew</h3>
    <div class="crew-container">
      <div class="crew-container-carrousel" :style="{ transform: 'translateX(' + (-currentIndex * 100) + '%)', gridTemplateColumns: `repeat(${members.length}, 100%)` }">
        <CrewMember v-for="member, i in members" :key="member.id" :member="member" :isActive="currentIndex === i"></CrewMember>
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
      interval: null,
      members: [
        {
          id: 1,
          name: "##### ###### ##### ######",
          rol: "##### ###### ##### ###### ######",
          image: stevenImg
        },
        {
          id: 2,
          name: "##### ###### ##### ######",
          rol: "##### ###### ##### ###### ######",
          image: stevenImg
        },
        {
          id: 3,
          name: "##### ###### ##### ######",
          rol: "##### ###### ##### ###### ######",
          image: stevenImg
        },
        {
          id: 4,
          name: "##### ###### ##### ######",
          rol: "##### ###### ##### ###### ######",
          image: stevenImg
        },
        {
          id: 5,
          name: "##### ###### ##### ######",
          rol: "##### ###### ##### ###### ######",
          image: stevenImg
        },
        {
          id: 6,
          name: "##### ###### ##### ######",
          rol: "##### ###### ##### ###### ######",
          image: stevenImg
        },
        {
          id: 7,
          name: "##### ###### ##### ######",
          rol: "##### ###### ##### ###### ######",
          image: stevenImg
        },
      ]
    }
  },
  created() {
    this.automaticSlide();
  },
  methods: {
    prevSlide() {
      this.currentIndex = (this.currentIndex === 0) ? this.members.length - 1 : this.currentIndex - 1;
      clearInterval(this.interval);
      this.automaticSlide();
    },
    nextSlide() {
      this.currentIndex = (this.currentIndex === this.members.length - 1) ? 0 : this.currentIndex + 1;
      clearInterval(this.interval);
      this.automaticSlide();
    },
    automaticSlide() {
      this.interval = setInterval(this.nextSlide, 20000);
    }
  }
};
</script>
