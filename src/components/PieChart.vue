<template>
  <pie-chart
    :id="pieChartName"
    :plot="plot"
    background-color="#1fe0"
    :color="borderColor">
  </pie-chart>
</template>

<script>
import PieChart from '@tygr/vue-pie-chart'

export default {
  components: {
    PieChart
  },
  props: ['borderColor'],
  data: () => ({
    pieChartName: 'Pie' + Math.floor(Math.random() * 99999999),
    plot: [
      {
        value: 16.98,
        color: '#12c2e9',
        label: 'Python',
        id: 1
      },
      {
        value: 16.04,
        color: '#4aa9ea',
        label: 'SQL & NoSQL',
        id: 2
      },
      {
        value: 16.04,
        color: '#8b8bec',
        label: 'PHP',
        id: 3
      },
      {
        value: 16.04,
        color: '#c471ed',
        label: 'HTML/CSS',
        id: 4
      },
      {
        value: 14.15,
        color: '#d466bc',
        label: 'C/C++',
        id: 5
      },
      {
        value: 11.32,
        color: '#e65a89',
        label: 'JavaScript',
        id: 6
      },
      {
        value: 9.43,
        color: '#ef546f',
        label: 'Java',
        id: 7
      }
    ]
  }),
  mounted: function () {
    var pSvg = this.$el.querySelector('#' + this.pieChartName + ' > svg')
    const {
      x,
      y,
      width,
      height
    } = pSvg.getBBox()
    const viewBoxValue = [x, y, width, height].join(' ')
    pSvg.setAttribute('viewBox', viewBoxValue)
  }
}
</script>

<style>
.pie-chart{
  width: 100% !important;
  max-width : 800px;
}
</style>
