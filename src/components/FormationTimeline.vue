<template>
  <div class="timelineContainer">
    <h2>{{title}}</h2>
    <timeline timeline-bg="#2196f3" timeline-theme="#b3d4fc">
      <br>
      <timeline-item v-for="(ei) in Object.keys(data)" :key="ei" :style="(parseInt(ei)<4 || showWholeList) ? 'max-height : 1000px;height: auto;' : 'border:none; margin: 0 0 0 28px; padding: 0; max-height : 0;overflow: hidden;display: block;'" icon-size="medium" :hollow="true" class="dropdown">
        <div class="row">
            <div class="col-3 blueDate" >
                <strong v-html="data[ei].date"></strong>
            </div>
            <div class="col-9 content">
                <p>
                    <strong v-html="data[ei].title"></strong><br>
                    <span v-html="data[ei].subtitle"></span>
                </p>
            </div>
        </div>
      </timeline-item>
    </timeline>
    <button class="showMore" @click="showWholeList = !showWholeList" v-html="(showWholeList) ? 'Afficher moins':'Afficher plus'"></button>
  </div>
</template>

<script>
import { Timeline, TimelineItem } from 'vue-cute-timeline'
import 'vue-cute-timeline/dist/index.css'
import 'bootstrap/dist/css/bootstrap-grid.css'

export default {
  components: {
    Timeline,
    TimelineItem
  },
  props: ['data', 'title'],
  data: () => ({
    showWholeList: false
  })
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
.timelineContainer .blueDate{
    color:#2196f3;
}
li.timeline-item{
    color:inherit !important;
}
@media only screen and (max-width: 449px) {
  .timelineContainer .content{
    margin-top: 0.3em;
  }
}


</style>
