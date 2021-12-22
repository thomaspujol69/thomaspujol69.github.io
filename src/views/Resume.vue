<template>
  <v-layout row justify-center align-center wrap class="mt-4 pt-2">
    <v-flex xs12 sm12 md5 lg6 xl6 class="mt-4 pt-4">
      <h2 class="mb-4 pl-4 pt-2">Formation</h2>
      <v-card-text class="py-0">
        <v-timeline align-top dense>

          <v-timeline-item color="blue" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold blue--text">SEP 2020 -</div>
                <div class="caption font-weight-bold blue--text">JUIL 2022</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>DUT Informatique</strong>
                <div class="caption mb-2">Université Claude Bernard Lyon 1</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>

          <v-timeline-item color="blue" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold blue--text">SEP 2020 -</div>
                <div class="caption font-weight-bold blue--text">PRESENT</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>Cours en ligne</strong>
                <div class="caption mb-2">France Université Numérique</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>

          <v-timeline-item color="blue" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold blue--text">SEP 2017 -</div>
                <div class="caption font-weight-bold blue--text">JUIL 2020</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>Baccalauréat scientifique spé. informatique</strong>
                <div class="caption mb-2">Lycée Institution des Chartreux Lyon I<sup>er</sup></div>
              </v-flex>
            </v-layout>
          </v-timeline-item>
        </v-timeline>
      </v-card-text>
    </v-flex>
    <v-flex xs12 sm12 md4 lg6 xl6 class="mt-4 pt-2">
      <h2 class="mb-4 pl-4">Expériences</h2>
      <v-card-text class="py-0">
        <v-timeline align-top dense>
          <v-timeline-item color="blue" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold blue--text">OCT 2021 -</div>
                <div class="caption font-weight-bold blue--text">JUIL 2022</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>Etudiant tuteur</strong>
                <div class="caption mb-2">Université Lyon 1</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>

          <v-timeline-item color="blue" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold blue--text">JUIN 2021 -</div>
                <div class="caption font-weight-bold blue--text">JUIL 2021</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>Stage volontaire - Cybersécurité</strong>
                <div class="caption mb-2">NSOC</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>

          <v-timeline-item color="blue" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold blue--text">MAI 2021 -</div>
                <div class="caption font-weight-bold blue--text">AUJOURD'HUI</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>Service Technique</strong>
                <div class="caption mb-2">BDE Info</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>

          <v-timeline-item color="blue" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold blue--text">AOUT 2020 -</div>
                <div class="caption font-weight-bold blue--text">AUJOURD'HUI</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>Concepteur et mainteneur d'applications web</strong>
                <div class="caption mb-2">Wado Club de Lyon</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>
        </v-timeline>
      </v-card-text>
    </v-flex>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-flex xs12 sm12 md4 lg5 xl5 class="mx-2 pt-4">
        <h2>
          <span>Compétences de </span>

          <span class="blue--text">développement</span>
        </h2>
        <br>
        <strong>Python</strong>
        <v-progress-linear v-model="bufferPython" :buffer-value="bufferValue" color="blue" height="16"></v-progress-linear>
        <strong>SQL & NoSQL</strong>
        <v-progress-linear v-model="bufferSQL" :buffer-value="bufferValue" color="blue" height="16"></v-progress-linear>
        <strong>C</strong>
        <v-progress-linear v-model="bufferC" :buffer-value="bufferValue" color="blue" height="16"></v-progress-linear>
        <strong>C++</strong>
        <v-progress-linear v-model="bufferCpp" :buffer-value="bufferValue" color="blue" height="16"></v-progress-linear>
      </v-flex>
      <v-flex xs12 sm12 md4 lg5 xl5 class="mx-2 pt-4">
        <h2>
          <span> </span>
          <span class="blue--text">&nbsp;</span>
        </h2>
        <br>
        <strong>PHP</strong>
        <v-progress-linear v-model="bufferPHP" :buffer-value="bufferValue" color="blue" height="16"></v-progress-linear>
        <strong>HTML/CSS</strong>
        <v-progress-linear v-model="bufferHTML" :buffer-value="bufferValue" color="blue" height="16"></v-progress-linear>
        <strong>JavaScript</strong>
        <v-progress-linear v-model="bufferJS" :buffer-value="bufferValue" color="blue" height="16"></v-progress-linear>
        <strong>Java</strong>
        <v-progress-linear v-model="bufferJava" :buffer-value="bufferValue" color="blue" height="16"></v-progress-linear>
      </v-flex>
      <div class="mt-4 pt-2">
        <v-btn
          href="/resources/docs/PUJOL_Thomas_CV.pdf"
          target="_blank"
          color="blue"
          dark
          large
        >
          Télécharger mon CV
          <v-icon right dark>fas fa-file-download</v-icon>
        </v-btn>
      </div>
    </v-layout>
  </v-layout>
</template>

<script>
export default {
  metaInfo: {
    title: 'Curriculum Vitae',
    titleTemplate: '%s ← Thomas PUJOL',
    meta: [
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      {
        name: 'description',
        content:
          'PHP HTML CSS JavaScript C Java Python Design Adobe Coding Skills Resume CV Work Web Software Developer Front-End Back-End'
      },
      { charset: 'utf-8' },
      { property: 'og:title', content: 'Thomas PUJOL' },
      { property: 'og:site_name', content: 'Thomas PUJOL' },
      { property: 'og:type', content: 'website' },
      { property: 'og:url', content: 'https://pujol.fr.eu.org' },
      {
        property: 'og:image',
        content: '/resources/images/IMG_0211.jpg'
      },
      {
        property: 'og:description',
        content:
          'PHP HTML CSS JavaScript C Java Python Design Adobe Coding Skills Resume CV Work Web Software Developer Front-End Back-End'
      }
    ]
  },
  data () {
    return {
      value: 0,
      buffer1: 0,
      bufferCpp: 0,
      bufferC: 0,
      bufferPython: 0,
      bufferJava: 0,
      bufferSQL: 0,
      bufferPHP: 0,
      bufferHTML: 0,
      bufferJS: 0,
      bufferValue: 100,
      interval: 0
    }
  },
  mounted () {
    this.startBuffer()
  },

  beforeDestroy () {
    clearInterval(this.interval)
  },

  methods: {
    startBuffer () {
      this.interval = setInterval(() => {
        this.buffer1 = 90
        this.bufferCpp = 75
        this.bufferC = 85
        this.bufferPython = 100
        this.bufferSQL = 95
        this.bufferPHP = 95
        this.bufferHTML = 95
        this.bufferJS = 75
        this.bufferJava = 70
      }, 800)
    }
  }
}
</script>
<style >
</style>
