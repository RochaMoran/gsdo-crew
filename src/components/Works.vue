<template>
  <section class="container-works" id="works">
    <TitleComponent title="WORKS" />
    <div class="section works" >
      <article class="work-one">
        <WorkComponent :title="items[0].title" :img="items[0].img" @click="showModal(items[0].images, items[0].title)"/>
      </article>
      <article class="work-container">
        <WorkComponent title="/Imodium® Ad Campaign" :img="imgImodium" @click="showModal([imgImodium], '/Imodium® Ad Campaign')"/>
        <WorkComponent title="/Healthy Essentials" :img="imgHealthyEssentials" @click="showModal([imgHealthyEssentials], '/Healthy Essentials')"/>
      </article>
      <article class="work-container">
        <WorkComponent title="/Listerine Total Care" :img="imgListerine" @click="showModal([imgListerine], '/Listerine Total Care')" />
        <WorkComponent title="/Neutrogea #1" :img="imgNeutrogea1" @click="showModal([imgNeutrogea1], '/Neutrogea #1')" />
      </article>
      <article class="work-one">
        <WorkComponent title="/Neutrogea Deep Clean" :img="imgNeutrogea2" @click="showModal([imgNeutrogea2], '/Neutrogea Deep Clean')" />
      </article>
      <article class="work-one">
        <WorkComponent :title="items[1].title" :img="items[1].img" @click="showModal(items[0].images, items[0].title)" />
      </article>
      <article class="work-container">
        <WorkComponent title="/Exjade deferasirox" :img="imgExjade" @click="showModal([imgExjade], '/Exjade deferasirox')" />
        <WorkComponent title="/HSBC it´s not surprising here" :img="imgHsbc" @click="showModal([imgHsbc], '/HSBC it´s not surprising here')" />
      </article>
      <article class="work-container">
        <WorkComponent title="/HSBC" :img="imgHsbc2" @click="showModal([imgHsbc2], '/HSBC')" />
        <WorkComponent title="/Inter S&R" :img="imgInter" @click="showModal([imgInter], '/Inter S&R')" />
      </article>
      <article class="work-one">
        <WorkComponent title="/Abbott " :img="imgAbbott" @click="showModal([imgAbbott], '/Abbott')" />
      </article>
      <article class="work-one">
        <WorkComponent title="/Children's Pepto " :img="imgPepto" @click="showModal([imgPepto], '/Childrens Pepto')" />
      </article>
      <article class="work-container">
        <WorkComponent title="/Risk & energy risk" :img="imgRisk" @click="showModal([imgRisk], '/Risk & energy risk')" />
        <WorkComponent title="/Union Square Lofts" :img="imgUnionSquare" @click="showModal([imgUnionSquare], '/Union Square Lofts')" />
      </article>
      <article class="work-container">
        <WorkComponent title="/Listerine Smart Rinse" :img="imgListerineSmartRinse" @click="showModal([imgListerineSmartRinse], '/Listerine Smart Rinse')" />
        <WorkComponent title="/Prilosec" :img="imgPrilosec" @click="showModal([imgPrilosec], '/Prilosec')" />
      </article>
      <article class="work-one">
        <WorkComponent title="/Somos World Vaccine" :img="imgSomosWorldVaccine" @click="showModal([imgSomosWorldVaccine], '/Somos World Vaccine', 'https://somos-world-vaccine-congress-2022.vercel.app/')" />
      </article>
      <article class="work-one">
        <WorkComponent title="/Dr. Ramon Tallaj Website" :img="imgFoundation" @click="showModal([imgFoundation], '/Dr. Ramon Tallaj Website', 'https://drramontallajfoundation.org/')" />
      </article>
      <article class="work-container">
        <WorkComponent title="/SOMOS Community Care - Expos22" :img="imgSomosExpoS22" @click="showModal([imgSomosExpoS22], '/SOMOS Community Care - Expos22', 'https://somos-exposd22.vercel.app/')" />
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
          title: "/Brasil Sul",
          img: imgBrasilSul,
          images: [
            imgBrasilSul,
            imgSkinFitness,
            imgMadeForWoman
          ]
        },
        {
          id: 2,
          title: "/European Gastronomic Festival",
          img: imgGastronomicFestival,
          images: [
            imgGastronomicFestival,
            imgGastronomicFestival2,
            imgGastronomicFestival3
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
