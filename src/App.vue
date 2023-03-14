<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <NavBar />
  <HeaderComponent />
  <WorksComponent />
</template>

<script>
import NavBar from './components/NavBar.vue'
import HeaderComponent from './components/Header.vue'
import WorksComponent from './components/Works.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    HeaderComponent,
    WorksComponent
  }
}
</script>

<style lang="scss">
  @import "./assets/sass/normalize.scss";
  @import "./assets/sass/variables.scss";
  @import "./assets/sass/styles.scss";
</style>
