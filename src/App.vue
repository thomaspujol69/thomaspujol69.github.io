<template>
  <v-app :dark="goDark">
    <v-content>
      <v-container align-center>
        <TheHeader :goDark="goDark" @changeTheme="updateTheme($event)"/>

        <transition
          name="router-animation"
          mode="out-in"
          enter-active-class="animated fadeIn fast"
          leave-active-class="animated fadeOut faster"
        >
          <router-view></router-view>
        </transition>
      </v-container>
    </v-content>
    <TheFooter/>
  </v-app>
</template>

<script>
import TheHeader from './components/TheHeader'
import TheFooter from './components/TheFooter'

export default {
  name: 'App',
  metaInfo: {
    title: 'Home',
    titleTemplate: '%s ← Thomas PUJOL',
    meta: [
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      { name: 'description', content: 'Portfolio de Thomas PUJOL' },
      { charset: 'utf-8' },
      { property: 'og:title', content: 'Thomas PUJOL' },
      { property: 'og:site_name', content: 'Thomas PUJOL' },
      { property: 'og:type', content: 'website' },
      { property: 'og:url', content: 'https://pujol.fr.eu.org' },
      {
        property: 'og:image',
        content: '/resources/images/IMG_0211.jpg'
      },
      { property: 'og:description', content: 'Portfolio de Thomas PUJOL' }
    ]
  },
  components: {
    TheHeader,
    TheFooter
  },
  data () {
    return { goDark: false }
  },
  methods: {
    updateTheme (updatedTheme) {
      this.goDark = !updatedTheme
    }
  }
}
</script>
<style>
@import "/resources/styles/animate.min.css";
</style>
