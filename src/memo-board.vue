<template>
  <el-scrollbar class="memo" :style="memoStyle(project.color)">
    <el-timeline :reverse="true">
      <el-timeline-item
        v-for="step in project.steps"
        :key="step.id"
        :color="project.color"
        :timestamp="step.timestamp">
        {{ content(step) }}
      </el-timeline-item>
    </el-timeline>
  </el-scrollbar>
</template>

<script>
export default {
  name: 'MemoBoard',
  props: ['project'],
  computed: {},
  methods: {
    memoStyle(color) {
      return {
        'border': `1px solid ${color}`,
        'border-right': `10px solid #00000000`,
        'background-color': `${color}22`
      }
    },
    content(step) {
      if (step.period) {
        return `${step.content} / ${step.period} min`
      }else if(step.point) {
        return `${step.content} / ${step.point} pts`
      } else if (step.buyAt) {
        return `[${step.content}] (${step.sellAt} - ${step.buyAt}) * ${step.quant} * 0.95 - 10 = ${parseInt((step.sellAt - step.buyAt) * step.quant * 0.95) - 10}`
      }
    }
  }
}

</script>