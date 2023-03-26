<template>
  <section class="section clients" id="clients">
    <TitleComponent title="CLIENTS" />
    <ul class="container-clients" >
      <li v-for="client in clients" :key="client.id">
        <img :src="client.image" :alt="client.name" />
      </li>
    </ul>
  </section>
</template>

<script>
import connectPartners from "@/assets/images/clients/connectpartners.svg";
import cv9 from "@/assets/images/clients/cv9.svg";
import donnestor from "@/assets/images/clients/donnestor.svg";
import dragados from "@/assets/images/clients/dragados.svg";
import fiberxel from "@/assets/images/clients/fiberxel.svg";
import gmf from "@/assets/images/clients/gmf.svg";
import healthfirst from "@/assets/images/clients/healthfirst.svg";
import legacies from "@/assets/images/clients/legacies.svg";
import leroy from "@/assets/images/clients/leroy.svg";
import rtf from "@/assets/images/clients/rtf.svg";
import shu from "@/assets/images/clients/shu.svg";
import somos from "@/assets/images/clients/somos.svg";
import unanue from "@/assets/images/clients/unanue.svg";
import viahr from "@/assets/images/clients/viahr.svg";
import TitleComponent from "@/components/Title.vue";

export default {
  name: "OurClients",
  components: {
    TitleComponent,
  },
  data() {
    return {
      clients: [
        {
          id: 1,
          image: donnestor,
          name: "Donnestor"
        },
        {
          id: 2,
          image: connectPartners,
          name: "Connect Partners"
        },
        {
          id: 3,
          image: cv9,
          name: "CV9"
        },
        {
          id: 4,
          image: dragados,
          name: "Dragados"
        },
        {
          id: 5,
          image: fiberxel,
          name: "Fiberxel"
        },
        {
          id: 6,
          image: gmf,
          name: "GMF"
        },
        {
          id: 7,
          image: healthfirst,
          name: "Healthfirst"
        },
        {
          id: 8,
          image: legacies,
          name: "Legacies"
        },
        {
          id: 9,
          image: leroy,
          name: "Leroy"
        },
        {
          id: 10,
          image: rtf,
          name: "RTF"
        },
        {
          id: 11,
          image: shu,
          name: "SHU"
        },
        {
          id: 12,
          image: somos,
          name: "Somos"
        },
        {
          id: 13,
          image: unanue,
          name: "Unanue"
        },
        {
          id: 14,
          image: viahr,
          name: "ViaHR"
        },
      ],
    };
  },
};
</script>
