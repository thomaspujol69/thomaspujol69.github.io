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
        color: '#AEF3E7',
        label: 'Python',
        id: 1
      },
      {
        value: 16.04,
        color: '#8EE3EF',
        label: 'SQL & NoSQL',
        id: 2
      },
      {
        value: 16.04,
        color: '#2196f3',
        label: 'PHP',
        id: 3
      },
      {
        value: 16.04,
        color: '#37718E',
        label: 'HTML/CSS',
        id: 4
      },
      {
        value: 14.15,
        color: '#254E70',
        label: 'C/C++',
        id: 5
      },
      {
        value: 11.32,
        color: '#8A425E',
        label: 'JavaScript',
        id: 6
      },
      {
        value: 9.43,
        color: '#C33C54',
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
