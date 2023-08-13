<script setup>
  import Carousel from './components/Carousel.vue';
  import PieChart from './components/PieChart.vue';
</script>

<template>
  <div>
    <div class="container mx-auto p-5 lg:p-20 flex flex-col lg:flex-row justify-center gap-10">
      <div class="mb-20 lg:mb-0">
        <Carousel />
      </div>
      <div>
        <PieChart />
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>
