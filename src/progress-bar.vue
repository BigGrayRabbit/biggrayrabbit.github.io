<template>
  <div class="row">
    <el-progress :text-inside="true" :stroke-width="18" :percentage="percentage" :color="project.color"></el-progress>
    <div class="count"> {{ sum }} / {{ project.target }}</div>
  </div>
</template>

<script>
export default {
  name: 'ProgressBar',
  props: ['project'],
  computed: {
    sum() {
      return this.calcSum(this.project)
    },
    percentage() {
      return this.calcPercentage(this.project)
    }
  },
  methods: {
    calcSum(project) {
      let sum = 0
      if (project.steps[0].period) {
        project.steps.forEach(s => {
          sum += s.period
        })
      } else if (project.steps[0].buyAt) {
        project.steps.forEach(m => {
          sum += (m.sellAt - m.buyAt) * m.quant * 0.95 // 扣5%算作摩擦费
        })
        sum = parseInt(sum)
      }
      return sum
    },
    calcPercentage(project) {
      let sum = this.calcSum(project)
      let tar = project.target
      return parseFloat(((sum / tar) * 100).toFixed(2))
    },
  }
}

</script>
