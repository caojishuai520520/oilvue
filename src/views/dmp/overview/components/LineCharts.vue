<template>
  <div id="charts"></div>
</template>

<script>
import { Chart } from '@antv/g2'

export default {
  data() {
    return {
      data: [
        { year: '1991', value: 3 },
        { year: '1992', value: 4 },
        { year: '1993', value: 3.5 },
        { year: '1994', value: 5 },
        { year: '1995', value: 4.9 },
        { year: '1996', value: 6 },
        { year: '1997', value: 7 },
        { year: '1998', value: 9 },
        { year: '1999', value: 13 },
        { year: '2000', value: 14 },
        { year: '2001', value: 15 },
        { year: '2002', value: 16 },
      ],
    }
  },
  methods: {
    init: function () {
      const chart = new Chart({
        container: 'charts',
        autoFit: true,
        height: 300,
      })

      chart.data(this.data)
      chart.scale({
        year: {
          range: [0, 1],
        },
        value: {
          min: 0,
          nice: true,
        },
      })

      chart.tooltip({
        showCrosshairs: true, // 展示 Tooltip 辅助线
        shared: true,
      })

      chart.line().position('year*value').label('value')
      chart.point().position('year*value')

      chart.render()
    },
  },

  mounted() {
    this.init()
    // this.basicBarChart()
  },
}
</script>

<style></style>
