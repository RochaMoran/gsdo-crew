<template>
  <section class="section container-works" id="works">
    <TitleComponent title="WORKS"/>
    <div class="works" >
      <article class="work-one">
        <WorkComponent :title="items[0].title" :img="items[0].img" @click="showModal(items[0].images, items[0].title)"/>
      </article>
      <article class="work-container">
        <WorkComponent title="/Imodium Ad Campaign" :img="imgImodium" @click="showModal([imgImodium], '/Imodium Ad Campaign')"/>
        <WorkComponent title="/Healthy Essentials Ad Campaign" :img="imgHealthyEssentials" @click="showModal([imgHealthyEssentials], '/Healthy Essentials Ad Campaign')"/>
      </article>
      <article class="work-container">
        <WorkComponent title="/Listerine Total Care Advertising" :img="imgListerine" @click="showModal([imgListerine], '/Listerine Total Care')" />
        <WorkComponent :title="items[2].title" :img="items[2].img" @click="showModal(items[2].images, items[2].title)" />
      </article>
      <article class="work-one">
        <WorkComponent title="/Prilosec Advertising" :img="imgPrilosec" @click="showModal([imgPrilosec], '/Prilosec')" />
      </article>
      <article class="work-one">
        <WorkComponent :title="items[1].title" :img="items[1].img" @click="showModal(items[1].images, items[1].title)" />
      </article>
      <article class="work-container">
        <WorkComponent title="/Exjade Ad Campaign" :img="imgExjade" @click="showModal([imgExjade], '/Exjade Ad Campaign')" />
        <WorkComponent :title="items[3].title" :img="items[3].img" @click="showModal(items[3].images, items[3].title)" />
      </article>
      <article class="work-container">
        <WorkComponent title="/Listerine Smart Rinse Advertising" :img="imgListerineSmartRinse" @click="showModal([imgListerineSmartRinse], '/Listerine Smart Rinse')" />
        <WorkComponent title="/Inter S&R Ad Campaign" :img="imgInter" @click="showModal([imgInter], '/Inter S&R')" />
      </article>
      <article class="work-one">
        <WorkComponent title="/FreeStyle Freedom Advertising" :img="imgAbbott" @click="showModal([imgAbbott], '/Abbott')" />
      </article>
      <article class="work-one">
        <WorkComponent title="/Children's Pepto Advertising" :img="imgPepto" @click="showModal([imgPepto], '/Childrens Pepto')" />
      </article>
      <article class="work-container">
        <WorkComponent title="/Risk & energy risk Advertising" :img="imgRisk" @click="showModal([imgRisk], '/Risk & energy risk')" />
        <WorkComponent title="/Union Square Lofts Ad Campaign" :img="imgUnionSquare" @click="showModal([imgUnionSquare], '/Union Square Lofts')" />
      </article>
      <article class="work-container">
        <WorkComponent title="/Dr. Ramon Tallaj Website" :img="imgFoundation" @click="showModal([imgFoundation], '/Dr. Ramon Tallaj Website', 'https://drramontallajfoundation.org/')" />
        <WorkComponent title="/Festival of Biologics Splash Page" :img="imgSomosExpoS22" @click="showModal([imgSomosExpoS22], '/SOMOS Community Care - Expos22', 'https://somos-exposd22.vercel.app/')" />
      </article>
      <article class="work-one">
        <WorkComponent title="/Worldvaccine Congress Splash Page" :img="imgSomosWorldVaccine" @click="showModal([imgSomosWorldVaccine], '/Somos World Vaccine', 'https://somos-world-vaccine-congress-2022.vercel.app/')" />
      </article>
    </div>
    </section>
  <ModalWork v-if="show" :item="selected" :changeShow="changeShow"/>
</template>

<script>
import WorkComponent from "./Work.vue";
import ModalWork from "./ModalWork.vue";
import TitleComponent from "./Title.vue";
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
    WorkComponent,
    ModalWork,
    TitleComponent
  },
  data() {
    return {
      items: [
        {
          id: 1,
          title: "/BrasilSul Ad Campaign",
          img: imgBrasilSul,
          images: [
            imgBrasilSul,
            imgSkinFitness,
            imgMadeForWoman
          ]
        },
        {
          id: 2,
          title: "/European Gastronomic Festival Ad Campaign",
          img: imgGastronomicFestival,
          images: [
            imgGastronomicFestival,
            imgGastronomicFestival2,
            imgGastronomicFestival3
          ]
        },
        {
          id: 3,
          title: "/Neutrogena Advertising",
          img: imgNeutrogea1,
          images: [
            imgNeutrogea1,
            imgNeutrogea2
          ]
        },
        {
          id: 4,
          title: "/HSBC Ad Campaign",
          img: imgHsbc,
          images: [
            imgHsbc,
            imgHsbc2
          ]
        },
      ],
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
      imgSomosWorldVaccine,
      show: false,
      selected: {
        title: "",
        img: "",
        type: null
      }
    };
  },
  methods: {
    showModal(images, title, url = null) {
      this.selected = {
        title: title,
        images: images,
        url: url || null
      };
      this.changeShow();
    },
    changeShow() {
      this.show = !this.show;
    }
  },
};
</script>
