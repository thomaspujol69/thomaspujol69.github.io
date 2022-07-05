<template>
  <div>
    <div class="slider">
      <div class="timelineContainer">
      <toggle-button :value="isHidden"
        @change="unHide"
        :labels="{checked: title1, unchecked: title2}"
        :width=165
        :height=40
        :font-size=20
        :color="{checked:'#37b0db', unchecked: '#CDD4DE'}"
        :switch-color="{ checked: '#187df0', unchecked: '#2196f3' }" >
      </toggle-button>
        <div :ref="title2" style="opacity:1;" class="timelineContainer">
          <timeline timeline-bg="#2196f3" timeline-theme="#b3d4fc">
            <br>
            <timeline-item v-for="(e) in data2" :key="e.title" icon-size="medium" :hollow="true">
              <div class="row">
                <div class="col-3 blueDate" >
                  <strong v-html="e.date"></strong>
                </div>
                <div class="col-9 content">
                  <p>
                      <strong v-html="e.title"></strong><br>
                      <span v-html="e.subtitle"></span>
                  </p>
                </div>
              </div>
            </timeline-item>
          </timeline>
        </div>
        <div :ref="title1" style="opacity: 0;display:none;" class="timelineContainer">
          <timeline timeline-bg="#2196f3" timeline-theme="#b3d4fc">
            <br>
            <timeline-item v-for="(e) in data1" :key="e.title" icon-size="medium" :hollow="true">
              <div class="row">
                <div class="col-3 blueDate" >
                  <strong v-html="e.date"></strong>
                </div>
                <div class="col-9 content">
                  <p>
                      <strong v-html="e.title"></strong><br>
                      <span v-html="e.subtitle"></span>
                  </p>
                </div>
              </div>
            </timeline-item>
          </timeline>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
import { Timeline, TimelineItem } from 'vue-cute-timeline'
import { ToggleButton } from 'vue-js-toggle-button'
import 'vue-cute-timeline/dist/index.css'
import 'bootstrap/dist/css/bootstrap-grid.css'
export default {
  components: {
    Timeline,
    TimelineItem,
    ToggleButton
  },
  data () {
    return {
      isHidden: false,
      unHide: (title1, title2) => {
        this.isHidden = !this.isHidden
        console.log(this.$refs[this.title1].style)
        if (this.isHidden) {
          setTimeout(() => {
            this.$refs[this.title2].style.opacity = 0
            setTimeout(() => {
              this.$refs[this.title2].style.display = 'none'
              this.$refs[this.title1].style.display = 'block'
              setTimeout(() => {
                this.$refs[this.title1].style.opacity = 1
              }, 15)
            }, 200)
          }, 200)
        } else {
          setTimeout(() => {
            this.$refs[this.title1].style.opacity = 0
            setTimeout(() => {
              this.$refs[this.title1].style.display = 'none'
              this.$refs[this.title2].style.display = 'block'
              setTimeout(() => {
                this.$refs[this.title2].style.opacity = 1
              }, 15)
            }, 200)
          }, 200)
        }
      }
    }
  },
  props: ['data1', 'title1', 'data2', 'title2', 'goDark']
}
</script>

<style>
.timeline{
  padding-left: 1px;
  font-family: 'Roboto', sans-serif !important;
}
.col-3{
    min-width: 95px;
}

.slider .timelineContainer {
  transition: opacity 0.2s;
  margin:unset;
}
.timelineContainer .blueDate{
    color:#2196f3;
}
li.timeline-item{
    color:inherit !important;
}
.vue-js-switch .v-switch-label{
  font-weight: 500!important;
}
.vue-js-switch:hover .v-switch-button{
  animation: mymove 1s infinite;
  background-color: #3499ec !important;
}
.vue-js-switch .v-switch-label{
  color:#000 !important;
}
@media only screen and (max-width: 449px) {
  .timelineContainer .content{
    margin-top: 0.3em;
  }
}
</style>
