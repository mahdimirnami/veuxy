<template>
  <div class="chart-container">
    <VChart :option="option" autoresize />
  </div>
</template>
<script setup>
import { SunburstChart } from "echarts/charts";
import * as echarts from "echarts/core";
import { CanvasRenderer } from "echarts/renderers";
import { ref } from "vue";
import VChart from "vue-echarts";

echarts.use([SunburstChart, CanvasRenderer]);

const option = ref({
  series: [
    {
      type: "sunburst",
      radius: [60, "90%"],
      itemStyle: {
        borderRadius: 7,
        borderWidth: 2,
      },
      data: [
        {
          name: "Grandpa",
          children: [
            {
              name: "Uncle Leo",
              value: 15,
              children: [
                {
                  name: "Cousin Jack",
                  value: 2,
                },
                {
                  name: "Cousin Mary",
                  value: 5,
                  children: [
                    {
                      name: "Jackson",
                      value: 2,
                    },
                  ],
                },
                {
                  name: "Cousin Ben",
                  value: 4,
                },
              ],
            },
            {
              name: "Father",
              value: 10,
              children: [
                {
                  name: "Me",
                  value: 5,
                },
                {
                  name: "Brother Peter",
                  value: 1,
                },
              ],
            },
          ],
        },
        {
          name: "Nancy",
          children: [
            {
              name: "Uncle Nike",
              children: [
                {
                  name: "Cousin Betty",
                  value: 1,
                },
                {
                  name: "Cousin Jenny",
                  value: 2,
                },
              ],
            },
          ],
        },
      ],
      label: {
        show: false,
      },
    },
  ],
});
</script>
<style scoped>
.chart-container {
  border-radius: 10px;
  background-color: white;
  block-size: 600px; /* حتماً ارتفاع بده */
  inline-size: 100%;
}
</style>
