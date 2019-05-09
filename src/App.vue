<template>
  <div id='pb'>
    <progress-bar :project='year2019.season2.aptitude'></progress-bar>
    <progress-bar :project='year2019.season2.expounding'></progress-bar>
    <progress-bar :project='year2019.season2.money'></progress-bar>

    <div class="row no-flex-wrap">
      <memo-board :project="year2019.season2.aptitude"></memo-board>
      <memo-board :project="year2019.season2.expounding"></memo-board>
      <memo-board :project="year2019.season2.money"></memo-board>
    </div>
  </div>
</template>

<script>
/* project.steps.content: code description
  S: stock

*/

// todo 1.webpack-dev-server以及热更新，2.打包发布自走脚本

import ProgressBar from './progress-bar.vue'
import MemoBoard from './memo-board.vue'

export default {
  name: 'App',
  components: { ProgressBar, MemoBoard },
  data() {
    return {
      year2019: {
        season2: {
          expounding: {
            color: '#13ce66',
            target: 2400,
            steps: [
              { id: 0, timestamp: '2019-05-05 21:00', content: '导读PDF，抄1题(200字)', period: 120 },
              { id: 1, timestamp: '2019-05-08 20:30', content: '导读PDF-过完-得方向', period: 30 },
            ],
          },
          aptitude: {
            color: '#409EFF',
            target: 6000,
            steps: [
              { id: 0, timestamp: '2019-04-09 19:00', content: '省考公告发布，在19课堂看中公的解读直播', period: 100 },
              { id: 1, timestamp: '2019-04-11 21:30', content: '粉笔-行测', period: 90 },
              { id: 2, timestamp: '2019-04-12 21:45', content: '粉笔-行测', period: 100 },
              { id: 3, timestamp: '2019-04-13 09:20', content: '乘地铁去虹桥，粉笔-行测，综合类', period: 40 },
              { id: 4, timestamp: '2019-04-13 16:20', content: '粉笔-行测答案-抄常识-找点写字的手感', period: 30 },
              { id: 5, timestamp: '2019-04-15 21:40', content: '粉笔-行测-资料(40)，听知乎live-申论(30)', period: 70 },
              { id: 6, timestamp: '2019-04-16 21:00', content: '听知乎live-申论', period: 40 },
              { id: 7, timestamp: '2019-04-16 22:00', content: '粉笔-行测-30个判断推理', period: 90 },
              { id: 8, timestamp: '2019-04-17 21:15', content: '大白-申论-1-快进', period: 60 },
              { id: 9, timestamp: '2019-04-18 00:10', content: '粉笔-行测-15个综合', period: 20 },
              { id: 10, timestamp: '2019-04-19 21:10', content: '韩菲-秒杀三类：3+2相同归大，3+2+1找两个最多，点名为真', period: 70 },
              { id: 11, timestamp: '2019-04-20 16:30', content: '粉笔-行测-15个数量-数组做差递推', period: 40 },
              { id: 12, timestamp: '2019-04-20 21:30', content: '大白-申论-2-大作文方法', period: 80 },
              { id: 13, timestamp: '2019-04-20 23:10', content: '粉笔-行测-15数量-数列见明显倍数做商，圈两个没规律圈三个试试', period: 60 },
              { id: 14, timestamp: '2019-04-21 16:30', content: '粉笔-行测-言语和综合', period: 70 },
              { id: 15, timestamp: '2019-04-21 21:00', content: '大白视频-考前准备(意思不大，故时间折半)', period: 40 },
              { id: 16, timestamp: '2019-04-21 22:00', content: '粉笔-行测-资料题-无语', period: 25 },
              { id: 17, timestamp: '2019-04-23 19:00', content: '粉笔-行测-综合(难)', period: 20 },
              { id: 18, timestamp: '2019-04-23 22:30', content: '粉笔-行测-言语、推理', period: 60 },
              { id: 19, timestamp: '2019-04-24 20:30', content: '粉笔-行测智能组卷-[跨106/对75/错30/空35/结53]', period: 120 },
              { id: 20, timestamp: '2019-04-25 21:40', content: '粉笔-行测智能组卷-过昨天的答案/未完！', period: 80 },
              { id: 21, timestamp: '2019-04-26 21:00', content: '粉笔-行测智能组卷-过完数量题耗时近3h！', period: 160 },
              { id: 22, timestamp: '2019-04-27 15:30', content: '粉笔-行测智能组卷-过推理判断', period: 60 },
              { id: 23, timestamp: '2019-04-28 21:00', content: '粉笔-行测智能组卷-[跨142/对79/错61/结57](数72min, 资瞎填)', period: 140 },
              { id: 24, timestamp: '2019-04-29 20:30', content: '粉笔-行测智能组卷-过完昨天的答案', period: 180 },
              { id: 25, timestamp: '2019-04-30 22:00', content: '粉笔-行测智能组卷-[跨154/对84/错36/空20/结60]', period: 140 },
              { id: 26, timestamp: '2019-05-01 16:00', content: '粉笔-行测智能组卷-对答案', period: 60 },
              { id: 27, timestamp: '2019-05-01 20:30', content: '粉笔-行测智能组卷-对答案', period: 120 },
              { id: 28, timestamp: '2019-05-02 16:00', content: '高照-容斥原理和最值问题', period: 70 },
              { id: 29, timestamp: '2019-05-02 20:40', content: '粉笔15年浙江-[跨149/对77/错43/结64]', period: 140 },
              { id: 30, timestamp: '2019-05-02 23:00', content: '粉笔15年浙江-对75道答案', period: 60 },
              { id: 31, timestamp: '2019-05-04 14:30', content: '粉笔15年浙江-对65道答案', period: 60 },
              { id: 32, timestamp: '2019-05-04 16:00', content: '粉笔-快速15题', period: 40 },
              { id: 33, timestamp: '2019-05-04 16:00', content: '欧阳-言语-2集', period: 140 },
              { id: 34, timestamp: '2019-05-05 19:40', content: '欧阳-言语-1集', period: 40 },
              { id: 35, timestamp: '2019-05-05 19:40', content: '欧阳-言语-1集-句子排序、接语', period: 40 },
              { id: 36, timestamp: '2019-05-05 21:00', content: '唐宋-数量-1集', period: 80 },
              { id: 37, timestamp: '2019-05-05 23:00', content: '粉笔行测-数量', period: 30 },
              { id: 38, timestamp: '2019-05-08 22:00', content: '粉笔行测-语言+判断', period: 40 },
            ],
          },
          money: {
            color: '#8e71c7',
            target: 30000,
            steps: [
              { id: 0, timestamp: '2019-04-08', content: 'S:601211', buyAt: 19.4, sellAt: 20.53, quant: 4300 },
            ]
          }
        }
      },
    }
  },
}

</script>
