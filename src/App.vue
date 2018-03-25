<template>

  <v-app dark>
    <app-header></app-header>
      <router-view />
    <app-footer></app-footer>
  </v-app>
</template>

<script>
  import Footer from './layout/Footer'
  import Header from './layout/Header'


  export default {
    components: {
      appFooter: Footer,
      appHeader: Header,
    },
    name: 'App'
  }
</script>
