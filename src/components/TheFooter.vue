<template>
  <v-footer class="pa-3">
    <button id="credits-button" @click="showModal=!showModal">Credits</button>
    <v-spacer></v-spacer>
    <div>&copy; Thomas PUJOL {{ new Date().getFullYear() }}</div>
    <v-spacer></v-spacer>
    Créé avec&nbsp;
    <v-icon small color="red">fas fa-heart</v-icon>&nbsp;et&nbsp;
    <v-icon small color="green">fab fa-vuejs</v-icon>
    <transition name="modal">
        <div v-if="showModal" class="modal-mask">
          <div class="modal-wrapper">
            <div class="modal-container">

              <div class="modal-header">
                <slot name="header">
                  <h1>Crédits & Mentions légales</h1>
                </slot>
              </div>
              <div class="modal-body">
                <slot name="body">
                  <h2>Mentions Légales</h2>
                  <h4>Propriétaire du site</h4>
                  <p>
                    PUJOL Thomas<br>
                    SIREN : 909 562 431 <br>
                  </p>
                  <h4>Contact</h4>
                  <p>
                    thomaspujol69@gmail.com<br>
                    61 rue Coste <br>
                    69300 Caluire-et-Cuire
                  </p>
                  <h4>Hébergeur</h4>
                  <p>
                    Github Pages <br>
                    88 Colin P Kelly Junior Street <br>
                    San Francisco, CA 94107 USA <br>
                    (415) 448-6673
                  </p>
                  <h2>Crédits</h2>
                  <p>

                  </p>
                </slot>
              </div>

              <div class="modal-footer">
                <slot name="footer">
                  &nbsp;
                  <button class="modal-default-button" @click="showModal=!showModal">
                    Fermer
                  </button>
                </slot>
              </div>
            </div>
          </div>
        </div>
      </transition>
  </v-footer>
</template>

<script>
export default {
  name: 'SizeModalTest',
  data: () => {
    return {
      showModal: true
    }
  },
  methods: {
    show () {
      this.$modal.show('credits-modal')
    },
    hide () {
      this.$modal.hide('credits-modal')
    }
  }
}
</script>

<style lang="scss" scoped>
.size-modal-content {
  padding: 10px;
  font-style: 13px;
}
.v--modal-overlay[data-modal='size-modal'] {
  background: rgba(0, 0, 0, 0.5);
}
.demo-modal-class {
  border-radius: 5px;
  background: #f7f7f7;
  box-shadow: 5px 5px 30px 0px rgba(46, 61, 73, 0.6);
}
.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: table;
  transition: opacity 0.3s ease;
}

.modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}

.modal-container {
  width: 80%;
  margin: 0px auto;
  padding: 20px 30px;
  background-color: #fff;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
  transition: all 0.3s ease;
  font-family: Helvetica, Arial, sans-serif;
}

.modal-header h3 {
  margin-top: 0;
  color: #42b983;
}

.modal-body {
  margin: 20px 0;
}

.modal-default-button {
  float: right;
}

/*
 * The following styles are auto-applied to elements with
 * transition="modal" when their visibility is toggled
 * by Vue.js.
 *
 * You can easily play with the modal transition by editing
 * these styles.
 */

.modal-enter {
  opacity: 0;
}

.modal-leave-active {
  opacity: 0;
}

.modal-enter .modal-container,
.modal-leave-active .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
</style>
