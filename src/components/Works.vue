<template>
  <h3 class="works-title" id="works">Works Done</h3>
  <section class="section works">
    <WorkComponent v-for="work in works" :title="work.title" :url="work.url" :imgUrl="work.img" :description="work.description" :key="work.id" />
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
          img: imgFoundation,
          url: 'https://drramontallajfoundation.org/store'
        },
        {
          id: 2,
          title: "Foundation Website",
          description: "A website for a foundation",
          img: imgFoundationWs,
          url: 'https://drramontallajfoundation.org/'
        },
        {
          id: 3,
          title: "SOMOS exposd22",
          description: "A expo for a SOMOS",
          img: imgSomosExpoS22,
          url: 'https://somos-exposd22.vercel.app/'
        },
        {
          id: 4,
          title: "SOMOS landingpage work",
          description: "A landingpage for a SOMOS",
          img: imgSomosLandingpage,
          url: 'https://somoscommunitycare.org/back-to-school/'
        },
        {
          id: 5,
          title: "SOMOS world vaccine",
          description: "A world vaccine for a SOMOS",
          img: imgSomosWorldVaccine,
          url: 'https://somos-world-vaccine-congress-2022.vercel.app/'
        },
      ]
    }
  }
};
</script>
