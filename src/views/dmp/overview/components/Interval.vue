<template>
  <div id="Interval" style="width: 600px; height: 400px"></div>
</template>

<script>
// import { Chart, registerShape } from '@antv/g2'

export default {
  data() {
    return {
      //   data: [
      //     { type: '分类一', value: 20 },
      //     { type: '分类二', value: 18 },
      //     { type: '分类三', value: 32 },
      //     { type: '分类四', value: 15 },
      //     { type: 'Other', value: 15 },
      //   ],
    }
  },
  methods: {
    drawChart() {
      // 基于准备好的dom，初始化echarts实例
      let myChart = this.$echarts.init(document.getElementById('Interval'))
      console.log(myChart)
      // 指定图表的配置项和数据
      let option = {
        tooltip: {
          trigger: 'item',
          formatter: '{a} <br/>{b}: {c} ({d}%)',
        },
        legend: {
          orient: 'vertical',
          left: 10,
          data: ['92#', '0#', '95#'],
        },
        series: [
          {
            name: '访问来源',
            type: 'pie',
            radius: ['50%', '70%'],
            avoidLabelOverlap: false,
            label: {
              show: false,
              position: 'center',
            },
            emphasis: {
              label: {
                show: true,
                fontSize: '30',
                fontWeight: 'bold',
              },
            },
            labelLine: {
              show: false,
            },
            data: [
              { value: 335, name: '92#' },
              { value: 310, name: '0#' },
              { value: 234, name: '95#' },
            ],
          },
        ],
      }
      // 使用刚指定的配置项和数据显示图表。
      myChart.setOption(option)
    },

    // init: function () {
    //   // 可以通过调整这个数值控制分割空白处的间距，0-1 之间的数值
    //   const sliceNumber = 0.01

    //   // 自定义 other 的图形，增加两条线
    //   registerShape('interval', 'slice-shape', {
    //     draw(cfg, container) {
    //       const points = cfg.points
    //       let path = []
    //       path.push(['M', points[0].x, points[0].y])
    //       path.push(['L', points[1].x, points[1].y - sliceNumber])
    //       path.push(['L', points[2].x, points[2].y - sliceNumber])
    //       path.push(['L', points[3].x, points[3].y])
    //       path.push('Z')
    //       path = this.parsePath(path)
    //       return container.addShape('path', {
    //         attrs: {
    //           fill: cfg.color,
    //           path,
    //         },
    //       })
    //     },
    //   })

    //   const chart = new Chart({
    //     container: 'Interval',
    //     autoFit: true,
    //     // width: 100,
    //     height: 300,
    //   })

    //   chart.data(this.data)
    //   chart.coordinate('theta', {
    //     radius: 0.75,
    //     innerRadius: 0.7,
    //   })
    //   chart.tooltip({
    //     showTitle: false,
    //     showMarkers: false,
    //   })
    //   chart.interval().adjust('stack').position('value').color('type').shape('slice-shape')

    //   chart.render()
    // },
  },

  mounted() {
    this.drawChart()
    // // this.basicBarChart()
  },
}
</script>

<style lang='scss'>
#Interval {
  width: 500px;
  height: 500px;
}
</style>
