<template>
  <v-content>
    <app-get-started></app-get-started>
    <app-showcase></app-showcase>
    <app-headline-parallax></app-headline-parallax>
    <app-info-row></app-info-row>
  </v-content>
</template>

<script>
  import GetStarted from '../components/GetStarted'
  import Showcase from '../components/Showcase'
  import HeadlineParallax from '../components/HeadlineParallax'
  import InfoRow from '../components/InfoRow'

  export default {
    components: {
      appInfoRow: InfoRow,
      appGetStarted: GetStarted,
      appShowcase: Showcase,
      appHeadlineParallax: HeadlineParallax
    }
  }
</script>
