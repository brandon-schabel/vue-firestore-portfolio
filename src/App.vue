<template>
  <v-app>
    <v-container id="app">
      <app-crud></app-crud>
    </v-container>
  </v-app>
</template>

<script>
  import Crud from './components/Crud'
  export default {
    components: {
      appCrud: Crud
    },
    name: 'App'
  }
</script>
