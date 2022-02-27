<template>
  <v-layout row justify-center wrap class="mt-4 pt-2">
    <v-flex xs12 sm12 lg6 xl6 class="mt-4 pt-2">
      <formation-timeline :data="formation" title="Formation"></formation-timeline>
    </v-flex>
    <v-flex xs12 sm12 lg6 xl6 class="mt-4 pt-2">
      <formation-timeline :data="experiences" title="Expériences"></formation-timeline>
    </v-flex>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2 timelineContainer flexCompetences">
      <v-flex xl5 class="mx-2 pt-4">
        <h2>
          <span>Compétences en </span>
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
      <v-flex xl5 class="mx-2 pt-4">
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
import FormationTimeline from '../components/FormationTimeline.vue'
export default {
  components: { FormationTimeline },
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
      interval: 0,
      formation: [
        {
          date: 'JUIL 2022<br>SEP 2020',
          title: 'DUT Informatique',
          subtitle: 'Université Claude Bernard Lyon 1'
        },
        {
          date: 'AUJOURD\'HUI<br>SEP 2020',
          title: 'Formations en ligne',
          subtitle: 'France Université Numérique & Udemy'
        },
        {
          date: 'JUIL 2020<br>SEP 2017',
          title: 'Baccalauréat Scientifique spé. informatique',
          subtitle: 'Lycée Institution des Chartreux, Lyon I<sup>er</sup>'
        }
        // ,
        // {
        //   date: '',
        //   title: '',
        //   subtitle: ''
        // }
      ],
      experiences: [
        {
          date: 'AUJOURD\'HUI<br>JAN 2022',
          title: 'Auto-Entrepreneur',
          subtitle: 'Lyon'
        },
        {
          date: 'JUIL 2022<br>OCT 2021',
          title: 'Etudiant tuteur',
          subtitle: 'Université Claude Bernard Lyon 1'
        },
        {
          date: 'JUIL 2021<br>JUIN 2021',
          title: 'Stagiaire - Cybersécurité',
          subtitle: 'NSOC, Lyon'
        },
        {
          date: 'AUJOURD\'HUI<br>MAI 2021',
          title: 'Service Technique',
          subtitle: 'BDE Info Lyon 1'
        },
        {
          date: 'AUJOURD\'HUI<br>AOÛT 2020',
          title: 'Concepteur et mainteneur d\'applications web',
          subtitle: 'Wado Club de Lyon'
        }
      ]
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
<style>
.timelineContainer{
  max-width:600px;
  margin:auto;
}
.flexCompetences{
  flex-direction: row;
}
.flexCompetences > div{
  width:40%;
  min-width: 270px;
}
.flexCompetences>div:last-child{
  width:100%;
  text-align: center;
}
@media only screen and (min-width: 1264px) {
  .flexCompetences{
    max-width:unset;
  }
}
</style>
