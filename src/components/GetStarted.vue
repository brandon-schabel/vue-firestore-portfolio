<template>
  <section>
    <v-parallax src="https://c2.staticflickr.com/8/7050/6884552675_6538271f9e_b.jpg" height="600">
      <div>
        <v-layout
          row
          column
          align-center
          justify-center
          class="white--text header"
        >
          <img class="profile_image" src="../assets/profile_picture.jpg" alt="Vuetify.js" >
          <h1 class="white--text mb-2 display-1 text-xs-center">Brandon Schabel</h1>
          <v-layout>
            <a href="https://github.com/brandon-schabel"><img src="../assets/GitHub-Mark-Light-120px-plus.png" alt="github" height="60"></a>
            <a href="https://www.linkedin.com/in/brandon-schabel-7010b691/"><img src="../assets/LinkedIn_logo_initials.png" class="linkedin_logo" alt="linkedin" height="60"></a>
          </v-layout>
        </v-layout>
      </div>
    </v-parallax>
  </section>
</template>

<style>
  .profile_image {
    height: 200px;
    border-radius: 100%;
  }
  .header {
    align-items: center;
    justify-content: center;
  }

  .linkedin_logo {
    padding-left: 16px;
  }
</style>
