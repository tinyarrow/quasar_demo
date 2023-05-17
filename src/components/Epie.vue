<template>
  <div
    :id="chartId"
    :style="[{ width: '100%' }, { height: height + 'px' }]"
  ></div>
</template>
<script>
import echartsUtil from 'src/utils/echartsUtil';

export default {
  name: 'ePie',
  props: {
    height: {
      type: Number,
      default: 400,
    },
    theme: {
      type: String,
      default: 'light',
    },
    option: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      defaultOption: echartsUtil.defaultPieOption,
      myChart: {},
    };
  },
  computed: {
    chartId: function () {
      return 'Epie-' + Math.random().toString(36).substr(2);
    },
  },
  methods: {
    resize() {
      const self = this;
      if (self.myChart.resize) {
        self.myChart.resize();
      }
    },
  },
  watch: {
    option: {
      handler(newVal, oldVal) {
        echartsUtil.watchOptionRefresh(this, newVal, oldVal);
      },
      deep: true, // 对象内部属性的监听，关键。
    },
  },
  created() {
    this.$nextTick(() => {
      console.log('aaaa');

      echartsUtil.drawChart(this);
    });
    window.addEventListener('resize', this.resize);
  },
  beforeUnmount: function () {
    window.removeEventListener('resize', this.resize);
  },
};
</script>
