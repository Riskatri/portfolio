<template>
  <v-app>
    <v-toolbar class="white">
     <!-- <v-toolbar-side-icon><img :src="logo" alt="Vuetify.js" height="100%"></v-toolbar-side-icon> -->
      <v-toolbar-title class="mx-0" v-text="title"></v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn icon target="_blank" :href="twitter"> <v-icon style="padding-right:20px">mdi-twitter</v-icon> </v-btn>
        <v-btn icon target="_blank" :href="linkedin"> <v-icon style="padding-right:20px">mdi-linkedin</v-icon></v-btn>
        <v-icon style="padding-right:20px">mdi-instagram</v-icon>
      </v-toolbar-items>
    </v-toolbar>
    <v-main>
      <LandingPage/>
    </v-main>
  </v-app>
</template>

<script>
import LandingPage from './components/LandingPage';

export default {
  name: 'App',

  components: {
    LandingPage,
  },

  data: () => ({
    title: 'P O R T F O L I O ',
    linkedin: 'https://www.linkedin.com/in/riska-tri-handayani-a73986173/',
    twitter: 'https://twitter.com/Riskatrih'
  }),
  methods: {
  }
};
</script>
