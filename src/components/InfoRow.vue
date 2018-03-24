<template>
  <section>
    <v-container grid-list-xl>
      <v-layout row wrap justify-center class="my-5">
        <v-flex xs12 sm4>
          <app-about></app-about>
        </v-flex>
        <v-flex xs12 sm4 offset-sm1>
          <app-contact></app-contact>
        </v-flex>
      </v-layout>
    </v-container>
  </section>
</template>

<script>
  import About from './About'
  import Contact from './Contact'

  export default {
    components: {
      appAbout: About,
      appContact: Contact,
    },
    created: function () {
    },
    data() {
      return {
      }
    },
  }
</script>
