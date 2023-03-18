<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <NavBar />
  <HeaderComponent />
  <WorksComponent />
  <CrewComponent />
  <OurClients />
  <ContactForm />
  <FooterComponent />
</template>

<script>
import NavBar from './components/NavBar.vue'
import HeaderComponent from './components/Header.vue'
import WorksComponent from './components/Works.vue'
import CrewComponent from './components/Crew.vue'
import OurClients from './components/OurClients.vue'
import ContactForm from './components/ContactForm.vue'
import FooterComponent from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    HeaderComponent,
    WorksComponent,
    CrewComponent,
    OurClients,
    ContactForm,
    FooterComponent
  }
}
</script>

<style lang="scss">
  @import "./assets/sass/normalize.scss";
  @import "./assets/sass/variables.scss";
  @import "./assets/sass/styles.scss";
</style>
