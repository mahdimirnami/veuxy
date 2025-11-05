<template>
  <div class="chart-container">
    <VChart :option="option" autoresize />
  </div>
</template>

<script setup>
import { ref } from "vue";
import VChart from "vue-echarts";

// import echarts core modules
import { LineChart } from "echarts/charts";
import { GridComponent } from "echarts/components";
import * as echarts from "echarts/core";
import { UniversalTransition } from "echarts/features";
import { CanvasRenderer } from "echarts/renderers";

// رجیستر کردن ماژول‌ها
echarts.use([GridComponent, LineChart, CanvasRenderer, UniversalTransition]);

const option = ref({
  xAxis: {
    type: "category",
    boundaryGap: false,
    data: ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"],
  },
  yAxis: {
    type: "value",
  },
  series: [
    {
      data: [820, 932, 901, 934, 1290, 1330, 1320],
      type: "line",
      areaStyle: {},
    },
  ],
});
</script>

<style scoped>
.chart-container {
  border-radius: 10px;
  margin: auto;
  background-color: white;
  block-size: 600px;
  inline-size: 100%;
}
</style>
