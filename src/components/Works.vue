<template>
  <h3 class="works-title">Works Done</h3>
  <section class="section works">
    <WorkComponent v-for="work in works" :title="work.title" :imgUrl="work.img" :description="work.description" :key="work.id" />
  </section>
</template>

<script>
import WorkComponent from "./Work.vue";
import imgFoundation from "@/assets/images/foundation-store-work.webp";
import imgFoundationWs from "@/assets/images/foundation-website.webp";
import imgSomosExpoS22 from "@/assets/images/somos-exposd22.webp";
import imgSomosLandingpage from "@/assets/images/somos-landing-page-work.webp";
import imgSomosWorldVaccine from "@/assets/images/somos-world-vaccine.webp";

export default {
  name: "WorksComponent",
  components: {
    WorkComponent
  },
  data() {
    return {
      works: [
        {
          id: 1,
          title: "Foundation Store",
          description: "A store for a foundation",
          img: imgFoundation
        },
        {
          id: 2,
          title: "Foundation Website",
          description: "A website for a foundation",
          img: imgFoundationWs
        },
        {
          id: 3,
          title: "SOMOS exposd22",
          description: "A expo for a SOMOS",
          img: imgSomosExpoS22
        },
        {
          id: 4,
          title: "SOMOS landingpage work",
          description: "A landingpage for a SOMOS",
          img: imgSomosLandingpage
        },
        {
          id: 5,
          title: "SOMOS world vaccine",
          description: "A world vaccine for a SOMOS",
          img: imgSomosWorldVaccine
        },
      ]
    }
  }
};
</script>
