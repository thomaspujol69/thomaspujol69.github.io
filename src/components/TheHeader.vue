<template>
  <div>
    <v-navigation-drawer v-model="drawer" absolute temporary app width="150" height="340">
      <v-list class="pt-4">
        <v-list-tile active-class="blue--text" to="/">
          <v-list-tile-content>
            <v-list-tile-title>ACCUEIL</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
        <v-list-tile active-class="blue--text" to="/resume">
          <v-list-tile-content>
            <v-list-tile-title>RESUME</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
        <!--<v-list-tile active-class="blue--text" to="/services">
          <v-list-tile-content>
            <v-list-tile-title>SERVICES</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>-->
        <v-list-tile active-class="blue--text" to="/portfolio">
          <v-list-tile-content>
            <v-list-tile-title>PORTFOLIO</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
        <!--<v-list-tile active-class="blue--text" to="/blog">
          <v-list-tile-content>
            <v-list-tile-title>BLOG</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>-->
        <v-list-tile active-class="blue--text" to="/contact">
          <v-list-tile-content>
            <v-list-tile-title>CONTACT</v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar flat dense color="transparent" scroll-off-screen>
      <v-toolbar-side-icon class="hidden-md-and-up" @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-toolbar-title class="headline">
        <span class="font-weight-light">Thomas </span>
        <span class="blue--text">PUJOL</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn @click="changeTheme" depressed small icon class="hidden-md-and-up">
        <v-icon v-if="goDark==true">fas fa-sun</v-icon>
        <v-icon v-else>fas fa-moon</v-icon>
      </v-btn>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn flat to="/" active-class="blue--text headline">Accueil</v-btn>
        <v-btn flat to="/resume" active-class="blue--text headline">Resume</v-btn>
        <!--<v-btn flat to="/services" active-class="blue--text headline">Services</v-btn>-->
        <v-btn flat to="/portfolio" active-class="blue--text headline">Portfolio</v-btn>
        <!--<v-btn flat to="/blog" active-class="blue--text headline">Blog</v-btn>-->
        <v-btn flat to="/contact" active-class="blue--text headline">Contact</v-btn>
        <v-btn @click="changeTheme" depressed small icon>
          <v-icon v-if="goDark==true">fas fa-sun</v-icon>
          <v-icon v-else>fas fa-moon</v-icon>
        </v-btn>
      </v-toolbar-items>
    </v-toolbar>
  </div>
</template>

<script>
export default {
  props: {
    goDark: {
      type: Boolean
    }
  },
  data () {
    return {
      drawer: null
    }
  },
  methods: {
    changeTheme () {
      this.$emit('changeTheme', this.goDark)
    }
  }
}
</script>

<style >
</style>
