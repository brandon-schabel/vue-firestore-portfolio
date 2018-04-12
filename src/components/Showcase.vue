<template>
  <section>
    <v-layout
      column
      wrap
      class="my-5"
      align-center
    >
      <v-flex xs12 sm4 class="my-3">
        <div class="text-xs-center">
          <h2 class="headline">Skills</h2>
          <span class="subheading">
                Subheading
              </span>
        </div>
      </v-flex>
      <v-flex xs12>
        <v-container grid-list-xl>
          <v-layout row wrap align-center>
            <v-flex xs12 md4>
              <v-card class="elevation-0 transparent">
                <v-card-text class="text-xs-center">
                  <img src="../assets/React_Logo_128.png" alt="reactjs" height="128">
                  <!-- <v-icon x-large class="blue--text text--lighten-2">color_lens</v-icon> -->
                </v-card-text>
                <v-card-title primary-title class="layout justify-center">
                  <div class="headline text-xs-center">ReactJS</div>
                </v-card-title>
                <v-card-text>
                  Starting in 2018 I started learning React to widen my skill set with frontend frameworks and libraries.
                  Learning React and Vue at the same time has helped me understand how certain frontend libraries compare,
                  as well as knowing what the right tool for the job is.
                </v-card-text>
              </v-card>
            </v-flex>
            <v-flex xs12 md4>
              <v-card class="elevation-0 transparent">
                <v-card-text class="text-xs-center">
                  <img src="../assets/Vue_Logo_128.png" alt="vuejs" height="128">
                  <!--<v-icon x-large class="blue--text text--lighten-2">flash_on</v-icon>-->
                </v-card-text>
                <v-card-title primary-title class="layout justify-center">
                  <div class="headline">VueJS 2</div>
                </v-card-title>
                <v-card-text>
                  Toward the beginning of 2017 I started to learn VueJS 2 as my first frontend library. At the time
                  I had briefly tried Angular and React but ultimately felt they were not beginner friendly yet.
                  Starting from scratch Vue was by far the easiest and it has scaled nicely to some larger projects
                </v-card-text>
              </v-card>
            </v-flex>
            <v-flex xs12 md4>
              <v-card class="elevation-0 transparent">
                <v-card-text class="text-xs-center">
                  <v-icon x-large class="blue--text text--lighten-2">build</v-icon>
                </v-card-text>
                <v-card-title primary-title class="layout justify-center">
                  <div class="headline text-xs-center">HTML, CSS, JavaScript, Python</div>
                </v-card-title>
                <v-card-text>
                  Back in 2014 I had started playing around with HTML/CSS. Shortly after I had tried Python from
                  recommendations from multiple people. I prefer to use Python for backend when possible.
                </v-card-text>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
      </v-flex>
    </v-layout>
  </section>
</template>
