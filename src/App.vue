<template>
  <LoadingComponent />
  <template v-if="!loading">
    <NavBar/>
    <HeaderComponent />
    <WorksComponent />
    <CrewComponent />
    <OurClients />
    <ContactForm />
    <FooterComponent />
  </template>
</template>

<script>
import NavBar from './components/NavBar.vue'
import HeaderComponent from './components/Header.vue'
import WorksComponent from './components/Works.vue'
import CrewComponent from './components/Crew.vue'
import OurClients from './components/OurClients.vue'
import ContactForm from './components/ContactForm.vue'
import FooterComponent from './components/Footer.vue'
import LoadingComponent from './components/Loading.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    HeaderComponent,
    WorksComponent,
    CrewComponent,
    OurClients,
    ContactForm,
    FooterComponent,
    LoadingComponent
  },
  data() {
    return {
      loading: true
    }
  },
  mounted() {
    setTimeout(() => {
      this.loading = false
    }, 1450)
  }
}
</script>

<style lang="scss">
  @import "./assets/sass/normalize.scss";
  @import "./assets/sass/variables.scss";
  @import "./assets/sass/styles.scss";
</style>
