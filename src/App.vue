<template>

  <v-app dark>
    <app-header></app-header>
    <v-content>
      <app-get-started></app-get-started>
      <app-showcase></app-showcase>
      <app-headline-parallax></app-headline-parallax>
      <app-info-row></app-info-row>
      <app-footer></app-footer>
    </v-content>
  </v-app>
</template>

<script>
  import Footer from './layout/Footer'
  import Header from './layout/Header'

  import GetStarted from './components/GetStarted'
  import Showcase from './components/Showcase'
  import HeadlineParallax from './components/HeadlineParallax'
  import InfoRow from './components/InfoRow'
  export default {
    components: {
      appInfoRow: InfoRow,
      appFooter: Footer,
      appHeader: Header,
      appGetStarted: GetStarted,
      appShowcase: Showcase,
      appHeadlineParallax: HeadlineParallax
    },
    name: 'App'
  }
</script>
