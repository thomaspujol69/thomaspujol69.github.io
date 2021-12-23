<template>
  <v-container grid-list-xl>
    <h2 class="pl-4">
      <span class="blue--text">Portfolio</span>
      <span> Web</span>
    </h2>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
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
    title: 'Portfolio Web',
    titleTemplate: '%s ← Thomas PUJOL',
    meta: [
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      {
        name: 'description',
        content:
          'Portfolio des applications web de Thomas PUJOL NodeJS PHP HTML CSS JavaScript Developer Front-End Back-End Backend Frontend App Responsive'
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
          'Portfolio des applications web de Thomas PUJOL NodeJS PHP HTML CSS JavaScript Developer Front-End Back-End Backend Frontend App Responsive'
      }
    ]
  },
  data () {
    return {
      dialog: false,
      projects: [
        {
          dialog: false,
          title: 'My Mystery Academia',
          buttons: [
            {
              link: 'https://mymysteryacademia.bdeinfo.org/',
              icon: 'fas fa-desktop',
              name: 'Demo'
            }
          ],
          tech: ['Symfony', 'PHP', 'MySQL', 'HTML', 'CSS'],
          poster: '/resources/images/web/mma.png'
        },
        {
          dialog: false,
          title: 'SHDM URL Shortener',
          buttons: [
            {
              link: 'https://shdm.cf/',
              icon: 'fas fa-desktop',
              name: 'Demo'
            }
          ],
          tech: ['PHP', 'HTML', 'CSS'],
          poster: '/resources/images/web/shdm.png'
        },
        {
          dialog: false,
          title: 'Vitrine Wado Club de Lyon',
          buttons: [
            {
              link: 'https://www.karatewadoclubdelyon.fr/',
              icon: 'fas fa-desktop',
              name: 'Demo'
            }
          ],
          tech: ['PHP', 'WordPress', 'MySQL', 'HTML/CSS'],
          poster: '/resources/images/web/wadoWP.png'
        },
        {
          dialog: false,
          title: 'Inscriptions & Administration Wado Club de Lyon',
          buttons: [
            {
              link: 'https://www.karatewadoclubdelyon.fr/adherents',
              icon: 'fas fa-desktop',
              name: 'Demo'
            }
          ],
          tech: ['PHP', 'MySQL', 'HTML', 'CSS'],
          poster: '/resources/images/web/wadoInscr.png'
        },
        {
          dialog: false,
          title: 'Noël Canadien',
          buttons: [
            {
              link: 'https://github.com/BDEInfo/noelCanadien',
              icon: 'fab fa-github',
              name: 'Github'
            },
            {
              link: 'https://noelcanadien.bdeinfo.org/',
              icon: 'fas fa-desktop',
              name: 'Demo'
            }
          ],
          tech: ['PHP', 'HTML', 'CSS'],
          poster: '/resources/images/web/noelcanadien.png'
        },
        {
          dialog: false,
          title: 'Bistrot du Père',
          buttons: [
            {
              link: 'https://github.com/thomaspujol69/BDP_WEBAPP',
              icon: 'fab fa-github',
              name: 'Github'
            }
          ],
          tech: ['PHP', 'JavaScript', 'HTML', 'CSS'],
          poster: '/resources/images/web/bdp.png'
        },
        {
          dialog: false,
          title: 'Les Supers Mômes',
          buttons: [
            {
              link: 'http://les-supers-momes.epizy.com/',
              icon: 'fas fa-desktop',
              name: 'Demo'
            }
          ],
          tech: ['PHP', 'JavaScript', 'HTML', 'CSS'],
          poster: '/resources/images/web/bdp.png'
        },
        {
          dialog: false,
          title: 'API Bacle Visits',
          buttons: [
            {
              link: 'https://github.com/thomaspujol69/Bacle-Node-API',
              icon: 'fab fa-github',
              name: 'Github'
            },
            {
              link: 'http://api.bacle.eu.org/',
              icon: 'fas fa-desktop',
              name: 'Demo'
            }
          ],
          tech: ['JavaScript', 'NodeJS', 'MongoDB', 'Swagger'],
          poster: '/resources/images/web/bacle.png'
        },
        {
          dialog: false,
          title: 'Ski Club La Verpillière & Saint Quentin Fallavier',
          tech: ['PHP', 'MySQL', 'HTML', 'CSS', 'Composer'],
          poster: '/resources/images/web/sclvsqf.jpg'
        },
        {
          dialog: false,
          title: 'Annales - Institution des Chartreux',
          tech: ['PHP', 'HTML', 'CSS'],
          poster: '/resources/images/web/annales.png'
        }
      ]
    }
  }
}
</script>

<style  scoped>
</style>
