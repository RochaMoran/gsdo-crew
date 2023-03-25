<template>
  <section class="section clients" id="clients">
    <TitleComponent title="CLIENTS" />
    <ul class="container-clients" >
      <li v-for="client in clients" :key="client.id">
        <a href="#">
          <img :src="client.image" :alt="client.name" />
        </a>
      </li>
    </ul>
  </section>
</template>

<script>
import somosLogo from "@/assets/images/logo-somos.webp";
import foundationRamonTallajLogo from "@/assets/images/ramon-tallaj-foundation-logo.png";
import legacyLogo from "@/assets/images/logo-legacy-unidos.png";
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
          image: somosLogo,
          name: "Somos"
        },
        {
          id: 2,
          image: foundationRamonTallajLogo,
          name: "Fundación Ramón Tallaj"
        },
        {
          id: 2,
          image: legacyLogo,
          name: "Legacies Unidos"
        },
      ],
    };
  },
};
</script>
