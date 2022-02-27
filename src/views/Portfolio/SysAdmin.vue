<template>
  <v-container grid-list-xl>
    <h2 class="pl-4">
      <span class="blue--text">Portfolio</span>
      <span> SysAdmin</span>
    </h2>
    <v-layout justify-center align-center wrap class="mt-4 pt-2">
      <v-dialog
        v-model="project.dialog"
        lazy
        max-width="1000"
        v-for="project in projects"
        :key="project.title"
      >
        <template v-slot:activator="{ on }">
          <v-flex xs12 sm6 md4 lg4 xl4 v-on="on">
            <v-card hover flat color="transparent">
              <v-img
                :src="project.poster"
                :alt="project.title"
                height="230"
                lazy-src="/resources/images/fluid-loader.gif"
              ></v-img>
              <v-card-title primary-title class="justify-center">{{project.title}}</v-card-title>
            </v-card>
          </v-flex>
        </template>
        <v-card v-if="project.dialog">
          <v-img :src="project.poster"></v-img>
          <v-card-text>
            <h3 class="headline mb-0">
              <span>Technologies</span>
            </h3>
            <v-chip v-for="t in project.tech" :key="t" color="blue" text-color="white">{{t}}</v-chip>
          </v-card-text>
          <v-card-actions>
            <v-btn v-for="b in project.buttons" :key="b.name" flat large dark color="blue" :href="b.link" target="_blank">
              <v-icon left>{{ b.icon }}</v-icon>{{ b.name }}
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  metaInfo: {
    title: 'Portfolio SysAdmin',
    titleTemplate: '%s ← Thomas PUJOL',
    meta: [
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      {
        name: 'description',
        content:
          'Portfolio des administrations systèmes de Thomas PUJOL'
      },
      { charset: 'utf-8' },
      { property: 'og:title', content: 'Thomas PUJOL' },
      { property: 'og:site_name', content: 'Thomas PUJOL' },
      { property: 'og:type', content: 'website' },
      { property: 'og:url', content: 'https://www.pujol.fr.eu.org' },
      {
        property: 'og:image',
        content: '/resources/images/IMG_0211.jpg'
      },
      {
        property: 'og:description',
        content:
          'Portfolio des administrations systèmes de Thomas PUJOL'
      }
    ]
  },
  data () {
    return {
      dialog: false,
      projects: [
        {
          dialog: false,
          title: 'BDE Info',
          buttons: [
            {
              link: 'https://bdeinfo.org/',
              icon: 'fas fa-desktop',
              name: 'Demo'
            }
          ],
          tech: ['SSH', 'Docker', 'Portainer', 'Alpine', 'Nginx', 'Apache'],
          poster: '/resources/images/sysAdmin/bde.png'
        },
        {
          dialog: false,
          title: 'Home',
          tech: ['Raspberry Pi', 'NAS', 'Synology', 'HP Workstation'],
          poster: '/resources/images/sysAdmin/home.jpg'
        }
      ]
    }
  }
}
</script>

<style  scoped>
</style>
