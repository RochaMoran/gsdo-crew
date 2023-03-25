<template>
  <section class="section works" id="works">
    <article class="work-one">
      <WorkComponent title="/Imodium Ad Campaign" :img="imgFoundation" />
    </article>
    <article class="work-container">
      <WorkComponent title="/Foundation Store" :img="imgFoundationWs" />
      <WorkComponent title="/Foundation Website" :img="imgSomosExpoS22" />
    </article>
    <article class="work-container">
      <WorkComponent title="/Somos Landing Page" :img="imgSomosWorldVaccine" />
      <WorkComponent title="/Somos World Vaccine" :img="imgFoundation" />
    </article>
    <article class="work-one">
      <WorkComponent title="/Somos Expo SD22" :img="imgSomosLandingpage" />
    </article>
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
      imgFoundation,
      imgFoundationWs,
      imgSomosExpoS22,
      imgSomosLandingpage,
      imgSomosWorldVaccine
    };
  },
};
</script>
