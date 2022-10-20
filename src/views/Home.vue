<template>
  <v-layout column justify-center align-center class="mt-4 pt-2">
    <VueCompareImage
      class="hidden-md-and-down"
      hover
      :style="{ minWidth: '1300px' }"
      :sliderLineWidth="sliderLine"
      :handleSize="hSize"
      :leftImage="leftImage"
      :rightImage="rightImage"
      :sliderPositionPercentage="sliderPosition"
      v-if="!goDark"
    />
    <VueCompareImage
      class="hidden-md-and-down"
      hover
      :style="{ minWidth: '1300px' }"
      :sliderLineWidth="sliderLine"
      :handleSize="hSize"
      :leftImage="blackLeftImage"
      :rightImage="blackRightImage"
      :sliderPositionPercentage="sliderPosition"
      v-if="goDark"
    />
    <VueCompareImage
      class="hidden-lg-and-up"
      hover
      :style="{ maxWidth: '400px' }"
      :sliderLineWidth="sliderLine"
      :handleSize="hSize"
      :leftImage="leftImage2"
      :rightImage="rightImage2"
      :sliderPositionPercentage="sliderPosition"
    />

    <br>

    <vue-typer class="headline" :repeat="0" text=" Thomas PUJOL "> </vue-typer>
    <vue-typer
      :text="text1"
      :repeat="Infinity"
      :shuffle="false"
      initial-action="erasing"
      :pre-type-delay="70"
      :type-delay="70"
      :pre-erase-delay="1980"
      :erase-delay="150"
      erase-style="select-back"
      :erase-on-complete="false"
      caret-animation="smooth"
    ></vue-typer>
    <br>
    <v-flex xs12 sm6 md4 lg4 xl4>
      <v-card flat color="transparent" max-width="500">
        <v-card-title primary-title>
          <div>
            <h3 class="headline mb-0">
              <span>About</span>
              <span class="blue--text"> Me</span>
            </h3>
            <div>
              <p class="justify">
                Je suis étudiant à Télécom Paris, passionné d'informatique.
                Dynamique et doué d'un bon relationnel, je suis auto-entrepreneur et donne des cours d'informatique.
                Lorsque je ne suis pas à l'université, je pratique mon sport, le karaté, fais de la musique ou réalise un nouveau projet !
              </p>
            </div>
          </div>
        </v-card-title>

        <v-card-actions class="hidden-sm-and-down justify-center">
          <v-btn
            v-for="icon in icons"
            :key="icon.icon"
            fab
            dark
            outline
            color="blue"
            :href="icon.href"
            target="_blank"
          >
            <v-icon dark>{{icon.icon}}</v-icon>
          </v-btn>
        </v-card-actions>

        <v-card-actions class="hidden-md-and-up justify-center">
          <v-btn
            v-for="icon in icons"
            :key="icon.icon"
            small
            fab
            dark
            outline
            color="blue"
            :href="icon.href"
            target="_blank"
          >
            <v-icon dark>{{icon.icon}}</v-icon>
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
import { VueTyper } from 'vue-typer'
import VueCompareImage from 'vue-compare-image'

export default {
  props: {
    goDark: Boolean
  },
  metaInfo: {
    title: 'Thomas PUJOL',
    titleTemplate: 'Thomas PUJOL',
    meta: [
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      { name: 'description', content: 'Portfolio de Thomas PUJOL' },
      { charset: 'utf-8' },
      { property: 'og:title', content: 'Thomas PUJOL' },
      { property: 'og:site_name', content: 'Thomas PUJOL' },
      { property: 'og:type', content: 'website' },
      { property: 'og:url', content: 'https://pujol.eu.org' },
      {
        property: 'og:image',
        content: '/IMG_0211.jpg'
      },
      { property: 'og:description', content: 'Portfolio de Thomas PUJOL' }
    ]
  },
  components: {
    'vue-typer': VueTyper,
    VueCompareImage
  },
  data () {
    return {
      icons: [
        { href: 'https://github.com/thomaspujol69', icon: 'fab fa-github' },
        { href: 'https://twitter.com/thomaspujol69', icon: 'fab fa-twitter' },
        {
          href: 'https://www.linkedin.com/in/thomas-pujol',
          icon: 'fab fa-linkedin-in'
        },
        { href: 'https://www.malt.fr/profile/thomaspujol', icon: 'fas fa-malt' },
        {
          href: 'https://www.superprof.fr/etudiant-ecole-ingenieur-donne-cours-informatique-niveau-seconde-bac.html',
          icon: 'fas fa-superprof'
        },
        {
          href: 'https://www.facebook.com/thomaspujol69',
          icon: 'fab fa-facebook-f'
        },
        { href: 'https://www.instagram.com/thomaspujol69', icon: 'fab fa-instagram' },
        { href: 'https://musescore.com/thomaspujol69', icon: 'icon-musescore' }
      ],
      text1: ['Administrateur système', 'Administrateur réseau', 'Développeur web', 'Développeur logiciel'],
      leftImage: '/resources/images/leftImage.png',
      rightImage: '/resources/images/rightImage.png',
      blackLeftImage: '/resources/images/blackLeftImage.png',
      blackRightImage: '/resources/images/blackRightImage.png',
      leftImage2: '/resources/images/IMG_0211.jpg',
      rightImage2: '/resources/images/IMG_0211.jpg',
      sliderLine: 0,
      hSize: 0,
      sliderPosition: 0.5
    }
  }
}
</script>
<style>
@keyframes rocking {
  0%,
  100% {
    transform: rotateZ(-10deg);
  }

  50% {
    transform: rotateZ(10deg);
  }
}
.justify{
  text-align: justify;
}
.vue-typer {
  font-family: Arial, "Helvetica Neue", Helvetica, sans-serif;
}
.vue-typer .custom.char.typed {
  color: #2196f3;
}
.vue-typer .custom.char.selected {
  color: #e91e63;
}

.vue-typer .custom.caret {
  animation: rocking 1s ease-in-out 0s infinite;
}
.vue-typer .custom.caret.typing {
  background-color: #2196f3;
}
.vue-typer .custom.caret.selecting {
  display: inline-block;
  background-color: #e91e63;
}
.fa-malt:before {
  content: url("data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8' standalone='no'%3F%3E%3Csvg width='50' height='36.5' viewBox='0 0 50 36.5' fill='none' version='1.1' id='svg28' sodipodi:docname='malt_logo.svg' inkscape:version='1.2 (dc2aedaf03, 2022-05-15)' xmlns:inkscape='http://www.inkscape.org/namespaces/inkscape' xmlns:sodipodi='http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd' xmlns='http://www.w3.org/2000/svg' xmlns:svg='http://www.w3.org/2000/svg'%3E%3Cdefs id='defs32' /%3E%3Csodipodi:namedview id='namedview30' pagecolor='%23ffffff' bordercolor='%23666666' borderopacity='1.0' inkscape:showpageshadow='2' inkscape:pageopacity='0.0' inkscape:pagecheckerboard='0' inkscape:deskcolor='%23d1d1d1' showgrid='false' inkscape:zoom='8' inkscape:cx='25.875' inkscape:cy='28.75' inkscape:window-width='1920' inkscape:window-height='1017' inkscape:window-x='-8' inkscape:window-y='-8' inkscape:window-maximized='1' inkscape:current-layer='svg28' /%3E%3Cpath d='M 38.507179,5.26311 C 35.753874,2.5098043 32.812718,4.2918374 30.972104,6.1324517 L 13.584489,23.520652 c -1.840613,1.84042 -3.7671467,4.636878 -0.869341,7.534294 2.897806,2.898391 5.694266,0.971468 7.534489,-0.869146 L 37.637643,12.797991 C 39.478257,10.95718 41.26029,8.0160247 38.507179,5.26311 Z' fill='%23fc5656' id='path2' style='stroke-width:0.19527' /%3E%3Cpath d='M 21.895179,4.5509607 25.576992,8.23258 29.324612,4.4849595 C 29.579049,4.2299369 29.83739,3.9932698 30.097296,3.7700762 29.704802,1.7900393 28.574971,0 25.575235,0 c -3.0054,0 -4.133865,1.7970691 -4.52421,3.781402 0.280604,0.2427205 0.560621,0.4860267 0.844154,0.7695587 z' fill='%23fc5656' id='path4' style='stroke-width:0.19527' /%3E%3Cpath d='m 29.322464,31.899098 -3.745277,-3.745471 -3.679862,3.679469 c -0.279432,0.279627 -0.557496,0.535041 -0.834388,0.775027 0.421977,2.018505 1.616249,3.86732 4.512688,3.86732 2.904054,0 4.096763,-1.858775 4.516008,-3.883723 -0.257562,-0.22163 -0.515319,-0.438966 -0.769169,-0.692622 z' fill='%23fc5656' id='path6' style='stroke-width:0.19527' /%3E%3Cpath d='m 20.333604,13.476163 h -7.098061 c -2.602558,0 -5.9426498,0.819938 -5.9426498,4.71323 0,2.905031 1.8593603,4.097934 3.8846988,4.516983 0.239792,-0.276893 9.156012,-9.230213 9.156012,-9.230213 z' fill='%23fc5656' id='path8' style='stroke-width:0.19527' /%3E%3Cpath d='m 39.987911,13.665183 c -0.224561,0.261271 -9.159526,9.237245 -9.159526,9.237245 h 6.997302 c 2.602753,0 5.942649,-0.614906 5.942649,-4.713035 0,-3.005009 -1.796482,-4.134059 -3.780425,-4.52421 z' fill='%23fc5656' id='path10' style='stroke-width:0.19527' /%3E%3Cpath d='m 22.659269,11.146203 1.268082,-1.2680837 -3.67947,-3.6800569 c -1.84081,-1.8404188 -4.636879,-3.7671472 -7.534685,-0.8693417 -2.124927,2.1249274 -1.652961,4.1930315 -0.525863,5.8719613 0.343285,-0.02538 10.471936,-0.05448 10.471936,-0.05448 z' fill='%23fc5656' id='path12' style='stroke-width:0.19527' /%3E%3Cpath d='m 28.493543,25.232388 -1.271403,1.271401 3.748012,3.747622 c 1.840614,1.840809 4.781769,3.622453 7.534684,0.869537 2.05424,-2.054436 1.582857,-4.212167 0.447168,-5.940697 -0.365545,0.02636 -10.458461,0.05214 -10.458461,0.05214 z' fill='%23fc5656' id='path14' style='stroke-width:0.19527' /%3E%3C/svg%3E%0A");
}
.fa-superprof:before {
  content: url("data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiIHN0YW5kYWxvbmU9Im5vIj8+CjxzdmcKICAgaWQ9IkNhbHF1ZV8xIgogICBkYXRhLW5hbWU9IkNhbHF1ZSAxIgogICB2aWV3Qm94PSIwIDAgMzUuNzM2Nzk4IDM5LjMxMDc4NCIKICAgdmVyc2lvbj0iMS4xIgogICBzb2RpcG9kaTpkb2NuYW1lPSJOb3V2ZWF1IGRvY3VtZW50IHRleHRlLnR4dC5zdmciCiAgIHdpZHRoPSIzNS43MzY3OTciCiAgIGhlaWdodD0iMzkuMzEwNzgzIgogICBpbmtzY2FwZTp2ZXJzaW9uPSIxLjIuMSAoOWM2ZDQxZTQxMCwgMjAyMi0wNy0xNCkiCiAgIHhtbG5zOmlua3NjYXBlPSJodHRwOi8vd3d3Lmlua3NjYXBlLm9yZy9uYW1lc3BhY2VzL2lua3NjYXBlIgogICB4bWxuczpzb2RpcG9kaT0iaHR0cDovL3NvZGlwb2RpLnNvdXJjZWZvcmdlLm5ldC9EVEQvc29kaXBvZGktMC5kdGQiCiAgIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIKICAgeG1sbnM6c3ZnPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIKICAgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIgogICB4bWxuczpjYz0iaHR0cDovL2NyZWF0aXZlY29tbW9ucy5vcmcvbnMjIgogICB4bWxuczpkYz0iaHR0cDovL3B1cmwub3JnL2RjL2VsZW1lbnRzLzEuMS8iPgogIDxzb2RpcG9kaTpuYW1lZHZpZXcKICAgICBpZD0ibmFtZWR2aWV3MjEiCiAgICAgcGFnZWNvbG9yPSIjZmZmZmZmIgogICAgIGJvcmRlcmNvbG9yPSIjNjY2NjY2IgogICAgIGJvcmRlcm9wYWNpdHk9IjEuMCIKICAgICBpbmtzY2FwZTpzaG93cGFnZXNoYWRvdz0iMiIKICAgICBpbmtzY2FwZTpwYWdlb3BhY2l0eT0iMC4wIgogICAgIGlua3NjYXBlOnBhZ2VjaGVja2VyYm9hcmQ9IjAiCiAgICAgaW5rc2NhcGU6ZGVza2NvbG9yPSIjZDFkMWQxIgogICAgIHNob3dncmlkPSJmYWxzZSIKICAgICBpbmtzY2FwZTp6b29tPSIxMS40NDI0MjQiCiAgICAgaW5rc2NhcGU6Y3g9IjIxLjA2MTk3IgogICAgIGlua3NjYXBlOmN5PSIyOC4zNTkzNzUiCiAgICAgaW5rc2NhcGU6d2luZG93LXdpZHRoPSIxOTIwIgogICAgIGlua3NjYXBlOndpbmRvdy1oZWlnaHQ9Ijk5MSIKICAgICBpbmtzY2FwZTp3aW5kb3cteD0iLTEwIgogICAgIGlua3NjYXBlOndpbmRvdy15PSItMTAiCiAgICAgaW5rc2NhcGU6d2luZG93LW1heGltaXplZD0iMSIKICAgICBpbmtzY2FwZTpjdXJyZW50LWxheWVyPSJDYWxxdWVfMSIgLz4KICA8ZGVmcwogICAgIGlkPSJkZWZzMTQiPgogICAgPHN0eWxlCiAgICAgICBpZD0ic3R5bGUxMiI+LmNscy0xe2ZpbGw6I2ZhNjQ4NDt9PC9zdHlsZT4KICA8L2RlZnM+CiAgPHRpdGxlCiAgICAgaWQ9InRpdGxlMTYiPnNfcm9zZTwvdGl0bGU+CiAgPHBhdGgKICAgICBjbGFzcz0iY2xzLTEiCiAgICAgZD0iTSAzMy4wMjU1NjIsNy44NjIzOTE4IDIwLjU3OTYyOSwwLjcyMDk4OTAyIGEgNS40NTgxOTk3LDUuNDU4MTk5NyAwIDAgMCAtNS40MjI0NjQsMCBMIDIuNzEyNDIyNyw3Ljg2MjM5MTggQSA1LjM3ODM4NzcsNS4zNzgzODc3IDAgMCAwIDAsMTIuNTIwMDg3IFYgMjYuNzg5NzkgYSA1LjM3OTU3ODYsNS4zNzk1Nzg2IDAgMCAwIDIuNzEyNDIyNyw0LjY2NDg0MyBsIDEyLjQ0NDc0MjMsNy4xMzQyNTUgYSA1LjQ1MjI0MzksNS40NTIyNDM5IDAgMCAwIDUuNDIyNDY0LDAgTCAzMy4wMjU1NjIsMzEuNDU0NjMzIEEgNS4zNzk1Nzg2LDUuMzc5NTc4NiAwIDAgMCAzNS43MzY3OTYsMjYuNzg5NzkgViAxMi41MjAwODcgQSA1LjM3NzE5NjIsNS4zNzcxOTYyIDAgMCAwIDMzLjAyNTU2Miw3Ljg2MjM5MTggWiBNIDIzLjQ2MDAxNCwyNC41MTY5MyBhIDQuMjI0MDg5MSw0LjIyNDA4OTEgMCAwIDEgLTEuMzc0Njc0LDEuMzQ4NDY5IDYuNTUxNzQ1Niw2LjU1MTc0NTYgMCAwIDEgLTEuOTUzNjEzLDAuNzkwOTc1IDkuNTk1MzI5Niw5LjU5NTMyOTYgMCAwIDEgLTIuMjM1OTMyLDAuMjY1NjQxIDEyLjAwMTYwNywxMi4wMDE2MDcgMCAwIDEgLTMuNDc1OTk5LC0wLjQ5MzE2NiBxIC0xLjYzMzE3LC0wLjQ4NjAyMiAtMi42NTQwNTIsLTEuNTA5Mjg2IGwgMi4wNzI3MzUsLTIuNjY3MTU1IGEgNS40MDIyMTE5LDUuNDAyMjExOSAwIDAgMCAxLjc2NjU4OCwxLjAxMDE2MSA2LjA5NjY5NzMsNi4wOTY2OTczIDAgMCAwIDIuMTE2ODEsMC40MDYyMDcgNC40MzM3NDUxLDQuNDMzNzQ1MSAwIDAgMCAxLjU0ODU5NCwtMC4yMjc1MjUgcSAwLjYxMjI5LC0wLjIyODcxNSAwLjYxMjI5LC0wLjg5OTM3NiBhIDAuOTAwNTY3MjksMC45MDA1NjcyOSAwIDAgMCAtMC4xMjk4NDQsLTAuNDc2NDkgMS4yMTg2MjQ3LDEuMjE4NjI0NyAwIDAgMCAtMC40NzY0OTEsLTAuNDA2MjA4IDYuMTUxNDkzNSw2LjE1MTQ5MzUgMCAwIDAgLTAuOTc5MTg2LC0wLjM5MTkxNCBxIC0wLjYyNTM5NSwtMC4yMDI1MDggLTEuNTkxNDc5LC0wLjQ2MzM4NyBhIDEwLjY0ODM3NSwxMC42NDgzNzUgMCAwIDEgLTEuNTYxNjk5LC0wLjUzNzI0MyA1LjY3NTAwMjksNS42NzUwMDI5IDAgMCAxIC0xLjM3NDY3NSwtMC44MjU1MiAzLjgxMTkyNDgsMy44MTE5MjQ4IDAgMCAxIC0wLjk2MzcwMiwtMS4xOTEyMjUgMy43MDExNDA2LDMuNzAxMTQwNiAwIDAgMSAwLjA3MjY2LC0zLjM0OTczIDQuMjcyOTI5NSw0LjI3MjkyOTUgMCAwIDEgMS4yMTk4MTYsLTEuMzM1MzY0IDUuNzk2NTA4Miw1Ljc5NjUwODIgMCAwIDEgMS44MzMyOTcsLTAuODcwNzg4IDguMzIxOTA4Nyw4LjMyMTkwODcgMCAwIDEgMi4yODU5NjQsLTAuMzA0OTUzIDEwLjc1NDM5MiwxMC43NTQzOTIgMCAwIDEgMy4wNjYyMTcsMC4zOTE5MTMgOC43NTU1MTQ3LDguNzU1NTE0NyAwIDAgMSAyLjQyMjk1NCwxLjE0MzU3NyBsIC0xLjc4NjgzOSwyLjc1NjQ5OCBhIDguODY4NjgxLDguODY4NjgxIDAgMCAwIC0xLjUzMDcyNywtMC43ODI2MzUgNS4xNTA4NjMzLDUuMTUwODYzMyAwIDAgMCAtMS45NDE2OTgsLTAuMzQ5MDI5IHEgLTAuOTYzNzAyLDAgLTEuNDAwODgzLDAuMjc1MTcyIGEgMC44NDEwMDU5MiwwLjg0MTAwNTkyIDAgMCAwIC0wLjQzODM3MiwwLjczOTc1MiBxIDAsMC42NjgyNzkgMC45MDUzMzMsMC45ODUxNDQgMC45MDUzMzIsMC4zMTY4NjcgMi40NTI3MzYsMC43MjY2NDkgMi4xMDEzMjIsMC41Nzg5MzUgMy4wNTE5MjEsMS41OTI2NyAwLjk1MDU5OSwxLjAxMzczMyAwLjk1Mjk4MiwyLjY5NTc0NSBhIDMuNTY2NTMyLDMuNTY2NTMyIDAgMCAxIC0wLjUxMTAzNiwxLjk0NjQ2MyB6IgogICAgIGlkPSJwYXRoMTgiCiAgICAgc3R5bGU9InN0cm9rZS13aWR0aDowLjExOTEyMyIgLz4KICA8bWV0YWRhdGEKICAgICBpZD0ibWV0YWRhdGExODciPgogICAgPHJkZjpSREY+CiAgICAgIDxjYzpXb3JrCiAgICAgICAgIHJkZjphYm91dD0iIj4KICAgICAgICA8ZGM6dGl0bGU+c19yb3NlPC9kYzp0aXRsZT4KICAgICAgPC9jYzpXb3JrPgogICAgPC9yZGY6UkRGPgogIDwvbWV0YWRhdGE+Cjwvc3ZnPgo=");
}
</style>
