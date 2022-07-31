<template>
  <v-layout row justify-center wrap class="mt-4 pt-2">
    <v-flex xs12 sm12 lg6 xl6 class="mt-4 pt-2">
      <formation-double-timeline :goDark="goDark" :data2="formation" title2="Formation" :data1="experiences" title1="Expériences"></formation-double-timeline>
    </v-flex>
    <v-flex xs12 sm12 lg6 xl6 class="mt-4 pt-2">
      <formation-timeline :data="certifications" title="Certifications et MOOC"></formation-timeline>
    </v-flex>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2 timelineContainer flexCompetences">
      <h2 style="margin-top: 50px; margin-bottom: 20px;">
        <span>Mes </span>
        <span class="blue--text">langages</span>
        <span> favoris</span>
      </h2>
      <PieChart borderColor="#000" v-if="!goDark"/>
      <PieChart borderColor="#fff" v-if="goDark"/>
      <!--v-flex xl5 class="mx-2 pt-4">
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
      </v-flex-->
      <div class="pt-2" style="margin-top: 50px;">
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
import FormationDoubleTimeline from '../components/DoubleTimeline.vue'
import FormationTimeline from '../components/FormationTimeline.vue'
import PieChart from '../components/PieChart.vue'
export default {
  props: {
    goDark: Boolean
  },
  components: { FormationTimeline, FormationDoubleTimeline, PieChart },
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
      { property: 'og:url', content: 'https://pujol.eu.org' },
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
      certifications: [
        {
          date: 'JUIL 2022<br>FEV 2022',
          title: 'Cisco - Cybersecurity Pathway',
          subtitle: '<a target="_blank" href="https://www.credly.com/badges/850e2bb8-4980-48b8-b279-53004cd5e3a4">Connaissances en cybersécurité</a>'
        },
        {
          date: 'JAN 2022',
          title: 'TOEIC - 805/990',
          subtitle: 'Capacité professionnelle complète'
        },
        {
          date: 'DEC 2020',
          title: 'Sécurité des Réseaux Informatiques',
          subtitle: '<a target="_blank" href="https://lms.fun-mooc.fr/media/attestations/attestation_suivi_course-v1:MinesTelecom+04037+session01_c7d5ab3477de1494ed669bfade56be55.pdf">Institut Mines Télécom - <span title="France Université Numérique">FUN<span></a>'
        },
        {
          date: 'AVR 2020',
          title: 'Python : des fondamentaux aux concepts avancés du langage',
          subtitle: '<a target="_blank" href="https://lms.fun-mooc.fr/media/attestations/attestation_suivi_course-v1:UCA+107001+session02_ef52fbc87249017dea039994aada0a0d.pdf">Université Côte d\'Azur - <span title="France Université Numérique">FUN<span></a>'
        },
        {
          date: 'MAI 2022',
          title: 'S\'initier à l\'enseignement en Sciences Numériques et Technologie',
          subtitle: '<a target="_blank" href="https://lms.fun-mooc.fr/media/attestations/attestation_suivi_course-v1:inria+41018+session01_b53306b0e061fb4ecbdb6a46df7197b4.pdf">Inria - France Université Numérique</a>'
        },
        {
          date: 'DEC 2021',
          title: 'Je suis tuteur dans l\'enseignement supérieur',
          subtitle: '<a target="_blank" href="https://lms.fun-mooc.fr/media/attestations/attestation_suivi_course-v1:enseignementsup+131002+session01_164c142dfd144b9b14bbde3959ba3d26.pdf">Ministère de l\'Enseignement Supérieur - <span title="France Université Numérique">FUN<span></a>'
        },
        {
          date: 'AUJOURD\'HUI<br>SEP 2021',
          title: 'Ethical Hacking and Penetration Testing',
          subtitle: 'Udemy'
        }
      ],
      formation: [
        {
          date: 'JUIL 2025<br>SEP 2022',
          title: 'Cursus Ingénieur',
          subtitle: 'Institut National des Sciences Appliquées de Lyon'
        },
        {
          date: 'JUIL 2022<br>SEP 2020',
          title: 'DUT Informatique',
          subtitle: 'Université Claude Bernard Lyon 1'
        },
        {
          date: 'JUIL 2022<br>AVR 2022',
          title: 'Stagiaire - Systèmes et Réseaux',
          subtitle: 'Commune de Neuville-Sur-Saône'
        },
        {
          date: 'JUIL 2021<br>JUIN 2021',
          title: 'Stagiaire - Cybersécurité',
          subtitle: 'NSOC, Lyon'
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
          subtitle: 'Programmation, conseil et autres activités informatiques'
        },
        {
          date: 'JUIL 2022<br>OCT 2021',
          title: 'Etudiant tuteur',
          subtitle: 'Université Claude Bernard Lyon 1'
        },
        {
          date: 'AUJOURD\'HUI<br>AOÛT 2020',
          title: 'Concepteur et mainteneur d\'applications web',
          subtitle: 'Wado Club de Lyon'
        },
        {
          date: 'AUJOURD\'HUI<br>DEC 2017',
          title: 'Développeur & déployeur d\'applications',
          subtitle: 'SKI CLUB La Verpillière & Saint Quentin Fallavier, Bistrot du Père, ASC Caluire, CIL Caluire Sud - Clos Savaron'
        },
        {
          date: 'AVR 2022<br>MAI 2021',
          title: 'Service Technique',
          subtitle: 'BDE Info Lyon 1'
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
  margin:auto !important;
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

.timeline-item{
  -webkit-transition: all 1s ease;
  -moz-transition: all 1s ease;
  -ms-transition: all 1s ease;
  -o-transition: all 1s ease;
  transition: all 1s ease;
}

button.showMore{
  min-width : 140px;
  border: 1px solid black;
  border-radius: 1em;
  padding: 0.7em 1em;
  background-color: #82ccff;
  background-image: linear-gradient(0.375turn, rgba(71,196,196,255), rgba(35,98,98,0));
  transition: background-color 0.3s;
  font-weight: 500;
}
button.showMore:hover{
  background-color: #32ccff;
}
button.showMore:active{
  background-color: #128dff;
}
a{
  color: #2196f3;
}
</style>
