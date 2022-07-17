<template>
  <pie-chart 
    :plot="plot"
    background-color="#1fe0"
    :color="borderColor">
  </pie-chart>
</template>

<script>
import PieChart from '@tygr/vue-pie-chart'

export default {
  components: {
    PieChart,
  },
  props: ['borderColor'],
  data: () => ({
    plot: [
      {
        value: 16.98,
        color: '#1f01f5',
        label: 'Python',
        id: 1
      },
      {
        value: 16.04,
        color: '#2d0cf6',
        label: 'SQL & NoSQL',
        id: 2
      },
      {
        value: 16.04,
        color: '#3210f6',
        label: 'PHP',
        id: 3
      },
      {
        value: 16.04,
        color: '#4922f8',
        label: 'HTML/CSS',
        id: 4
      },
      {
        value: 14.15,
        color: '#592ff9',
        label: 'C/C++',
        id: 5
      },
      {
        value: 11.32,
        color: '#6538fa',
        label: 'JavaScript',
        id: 6
      },
      {
        value: 9.43,
        color: '#6e3ffa',
        label: 'Java',
        id: 7
      }
    ]
  })
}
</script>

<style>
.pie-chart{
  width: 100% !important;
}
</style>
