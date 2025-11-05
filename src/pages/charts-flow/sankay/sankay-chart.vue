<template>
  <div class="chart-container">
    <VChart :option="option" autoresize />
  </div>
</template>

<script setup>
import { SankeyChart } from "echarts/charts";
import * as echarts from "echarts/core";
import { CanvasRenderer } from "echarts/renderers";
import VChart from "vue-echarts";

echarts.use([SankeyChart, CanvasRenderer]);
// reactive option
const option = ref({
  series: {
    type: "sankey",
    layout: "none",
    emphasis: {
      focus: "adjacency",
    },
    data: [
      {
        name: "a",
      },
      {
        name: "b",
      },
      {
        name: "a1",
      },
      {
        name: "a2",
      },
      {
        name: "b1",
      },
      {
        name: "c",
      },
    ],
    links: [
      {
        source: "a",
        target: "a1",
        value: 5,
      },
      {
        source: "a",
        target: "a2",
        value: 3,
      },
      {
        source: "b",
        target: "b1",
        value: 8,
      },
      {
        source: "a",
        target: "b1",
        value: 3,
      },
      {
        source: "b1",
        target: "a1",
        value: 1,
      },
      {
        source: "b1",
        target: "c",
        value: 2,
      },
    ],
  },
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
