<template>
  <v-container grid-list-xl>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-flex xs12 sm12 md6 lg6 xl6>
        <h2 class="pb-4 mt-2">
          <span>Get In </span>
          <span class="blue--text">Touch</span>
        </h2>
        <div class="py-4 subheading font-weight-bold">
          <v-icon large color="blue" left>fas fa-map-marker-alt</v-icon>
          <span>Lyon,&nbsp;</span>
          <span class="blue--text">France</span>
        </div>
        <div class="py-4 subheading font-weight-bold">
          <v-icon large color="blue" left>fas fa-envelope</v-icon>
          <span>thomaspujol69@</span>
          <span class="blue--text">gmail.com</span>
        </div>
        <!--<div class="py-4 subheading font-weight-bold">
          <v-icon large color="blue" left>fas fa-phone</v-icon>
          <span>+33&nbsp;</span>
          <span class="blue--text">6 00 00 00 00</span>
        </div>-->
        <div class="py-4 subheading font-weight-bold">
          <v-icon large color="blue" left>fas fa-check</v-icon>
          <span>Freelance </span>
          <span class="blue--text">Disponible</span>
        </div>
      </v-flex>

      <v-flex xs12 sm12 md6 lg6 xl6>
        <h2 class="pb-4 mb-4">
          <span>Formulaire de </span>
          <span class="blue--text">Contact</span>
        </h2>

        <form method="POST" action="https://formspree.io/f/mvolojna">
          <v-text-field
            name="name"
            color="blue"
            background-color="transparent"
            v-model="name"
            :error-messages="nameErrors"
            label="Nom"
            required
            @blur="$v.name.$touch()"
          ></v-text-field>
          <v-text-field
            type="email"
            color="blue"
            background-color="transparent"
            name="email"
            v-model="email"
            :error-messages="emailErrors"
            label="E-mail"
            required
            @blur="$v.email.$touch()"
          ></v-text-field>
          <v-textarea
            color="blue"
            background-color="transparent"
            :counter="200"
            :error-messages="bodyErrors"
            v-model="body"
            label="Message"
            name="body"
            @blur="$v.body.$touch()"
          ></v-textarea>
          <v-btn
            @click="submit"
            type="submit"
            color="blue"
            class="white--text"
            :disabled=" (body.length<=20)"
          >ENVOYER</v-btn>
          <v-btn @click="clear">effacer</v-btn>
        </form>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import { validationMixin } from 'vuelidate'
import {
  required,
  maxLength,
  email,
  minLength
} from 'vuelidate/lib/validators'
export default {
  metaInfo: {
    title: 'Contact',
    titleTemplate: '%s ← Thomas PUJOL',
    meta: [
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      {
        name: 'description',
        content:
          'Contact - Thomas PUJOL'
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
          'Page de contact - Thomas PUJOL'
      }
    ]
  },
  mixins: [validationMixin],
  validations: {
    name: { required, maxLength: maxLength(20) },
    email: { required, email },
    body: { required, minLength: minLength(20) }
  },
  data () {
    return {
      name: '',
      email: '',
      body: ''
    }
  },
  methods: {
    submit () {
      this.$v.$touch()
    },
    clear () {
      this.$v.$reset()
      this.name = ''
      this.email = ''
      this.body = ''
    }
  },
  computed: {
    nameErrors () {
      const errors = []
      if (!this.$v.name.$dirty) return errors
      !this.$v.name.maxLength &&
        errors.push('Ce champ ne peut contenir plus de 20 caractères')
      !this.$v.name.required && errors.push('Votre nom est requis.')
      return errors
    },
    emailErrors () {
      const errors = []
      if (!this.$v.email.$dirty) return errors
      !this.$v.email.email && errors.push('L\'e-mail doit être valide')
      !this.$v.email.required && errors.push('L\'e-mail est requis.')
      return errors
    },
    bodyErrors () {
      const errors = []
      if (!this.$v.body.$dirty) return errors
      !this.$v.body.minLength &&
        errors.push('Ce champ doit contenir plus de 20 caractères')
      !this.$v.body.required && errors.push('Le message est requis.')
      return errors
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
