<template>
  <div class="timelineContainer">
    <h2>{{title}}</h2>
    <timeline timeline-bg="#2196f3" timeline-theme="#b3d4fc">
        <br>
        <timeline-item v-for="(e) in data" :key="e.title" icon-size="medium" :hollow="true">
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
  props: ['data', 'title']
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
