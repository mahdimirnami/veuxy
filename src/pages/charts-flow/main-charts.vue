<template>
  <div class="containercCharts">
    <firstChart></firstChart>
    <sankayChart></sankayChart>
    <SankeyLevel></SankeyLevel>
    <sunburstRound></sunburstRound>
    <drinkFlavor></drinkFlavor>
  </div>
</template>

<script setup>
import firstChart from "./line-charts/first-charts.vue";
import sankayChart from "./sankay/sankay-chart.vue";
import SankeyLevel from "./sankay/Sankey-level.vue";
import drinkFlavor from "./sun-burst/drink-flavor.vue";
import sunburstRound from "./sun-burst/sunburst-round.vue";
</script>

<style scoped>
.containercCharts {
  display: grid;
  gap: 10px;
  grid-template-columns: 1fr 1fr 1fr;
}

.chart-container {
  border-radius: 10px;
  margin: auto;
  background-color: white;
  block-size: 350px;
  inline-size: 100%;
}
</style>
