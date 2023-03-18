<template>
  <article class="section clients">
    <h3 class="works-title" id="clients">Our Clients</h3>
    <ul class="container-clients" >
      <li v-for="client in clients" :key="client.id">
        <a href="#">
          <img :src="client.image" :alt="client.name" />
        </a>
      </li>
    </ul>
  </article>
</template>

<script>
import somosLogo from "@/assets/images/logo-somos.webp";
import foundationRamonTallajLogo from "@/assets/images/ramon-tallaj-foundation-logo.png";
export default {
  name: "OurClients",
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
      ],
    };
  },
};
</script>
