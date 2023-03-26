<template>
  <section class="section works" id="works">
    <article class="work-one">
      <WorkComponent title="/BrasilSul And Campaign" :img="imgBrasilSul" />
    </article>
    <article class="work-container">
      <WorkComponent title="/Imodium® Ad Campaign" :img="imgImodium" />
      <WorkComponent title="/Healthy Essentials" :img="imgHealthyEssentials" />
    </article>
    <article class="work-container">
      <WorkComponent title="/Listerine Total Care" :img="imgListerine" />
      <WorkComponent title="/Neutrogea #1" :img="imgNeutrogea1" />
    </article>
    <article class="work-one">
      <WorkComponent title="/Made For Woman" :img="imgMadeForWoman" />
    </article>
    <article class="work-one">
      <WorkComponent title="/Made For Woman - Skin Fitness" :img="imgSkinFitness" />
    </article>
    <article class="work-container">
      <WorkComponent title="/Neutrogea Deep Clean" :img="imgNeutrogea2" />
      <WorkComponent title="/European Gastronomic Festival" :img="imgGastronomicFestival" />
    </article>
    <article class="work-container">
      <WorkComponent title="/European Gastronomic Festival #2" :img="imgGastronomicFestival2" />
      <WorkComponent title="/European Gastronomic Festival #3" :img="imgGastronomicFestival3" />
    </article>
    <article class="work-one">
      <WorkComponent title="/Abbott " :img="imgAbbott" />
    </article>
    <article class="work-one">
      <WorkComponent title="/Children's Pepto " :img="imgPepto" />
    </article>
    <article class="work-container">
      <WorkComponent title="/Exjade deferasirox" :img="imgExjade" />
      <WorkComponent title="/HSBC it´s not surprising here" :img="imgHsbc" />
    </article>
    <article class="work-container">
      <WorkComponent title="/HSBC" :img="imgHsbc2" />
      <WorkComponent title="/Inter S&R" :img="imgInter" />
    </article>
    <article class="work-one">
      <WorkComponent title="/Listerine Smart Rinse" :img="imgListerineSmartRinse" />
    </article>
    <article class="work-one">
      <WorkComponent title="/Prilosec" :img="imgPrilosec" />
    </article>
    <article class="work-container">
      <WorkComponent title="/Risk & energy risk" :img="imgRisk" />
      <WorkComponent title="/Union Square Lofts" :img="imgUnionSquare" />
    </article>
    <article class="work-container">
      <WorkComponent title="/Somos World Vaccine" :img="imgSomosWorldVaccine" />
      <WorkComponent title="/Dr. Ramon Tallaj Website" :img="imgFoundation" />
    </article>
    <article class="work-one">
      <WorkComponent title="/SOMOS Community Care - Expos22" :img="imgSomosExpoS22" />
    </article>
  </section>
</template>

<script>
import WorkComponent from "./Work.vue";
import imgBrasilSul from "@/assets/images/works/brasil-sul.jpg";
import imgImodium from "@/assets/images/works/imodium.jpg";
import imgHealthyEssentials from "@/assets/images/works/healthy-essentials.jpg";
import imgMadeForWoman from "@/assets/images/works/made-for-woman.jpg";
import imgListerine from "@/assets/images/works/listerine-total-care.webp";
import imgNeutrogea1 from "@/assets/images/works/neutrogea-rapid-results.jpg";
import imgNeutrogea2 from "@/assets/images/works/neutrogea-deep-clean.jpg";
import imgGastronomicFestival from "@/assets/images/works/european-gastronomic-festival.jpg";
import imgSkinFitness from "@/assets/images/works/skin-fitness.jpg";
import imgGastronomicFestival2 from "@/assets/images/works/european-gastronomic-festival-2.jpg";
import imgGastronomicFestival3 from "@/assets/images/works/european-gastronomic-festival-3.jpg";
import imgAbbott from "@/assets/images/works/abbott.jpg";
import imgPepto from "@/assets/images/works/childrens-pepto.jpg";
import imgExjade from "@/assets/images/works/exjade.jpg";
import imgHsbc from "@/assets/images/works/hsbc.jpg";
import imgHsbc2 from "@/assets/images/works/hsbc2.jpg";
import imgInter from "@/assets/images/works/inter.jpg";
import imgListerineSmartRinse from "@/assets/images/works/listerine-smart-rinse.jpg";
import imgPrilosec from "@/assets/images/works/prilosec.jpg";
import imgRisk from "@/assets/images/works/risk-energy-risk.jpg";
import imgUnionSquare from "@/assets/images/works/union-square-lofts.jpg";
import imgFoundation from "@/assets/images/works/foundation-website.webp";
import imgSomosExpoS22 from "@/assets/images/works/somos-exposd22.jpg";
import imgSomosLandingpage from "@/assets/images/works/somos-landing-page-work.webp";
import imgSomosWorldVaccine from "@/assets/images/works/somos-world-vaccine.webp";

export default {
  name: "WorksComponent",
  components: {
    WorkComponent
  },
  data() {
    return {
      imgBrasilSul,
      imgImodium,
      imgHealthyEssentials,
      imgMadeForWoman,
      imgListerine,
      imgNeutrogea1,
      imgNeutrogea2,
      imgGastronomicFestival,
      imgSkinFitness,
      imgGastronomicFestival2,
      imgGastronomicFestival3,
      imgAbbott,
      imgPepto,
      imgExjade,
      imgHsbc,
      imgHsbc2,
      imgInter,
      imgListerineSmartRinse,
      imgPrilosec,
      imgRisk,
      imgUnionSquare,
      imgFoundation,
      imgSomosExpoS22,
      imgSomosLandingpage,
      imgSomosWorldVaccine
    };
  },
};
</script>
