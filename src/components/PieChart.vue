<script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";

    // Sample data for the pie chart
    const chartData = ref({
        labels: ["Red", "Blue", "Yellow"],
        datasets: [
            {
            data: [300, 50, 100],
            backgroundColor: ["#FF6384", "#36A2EB", "#FFCE56"],
            hoverBackgroundColor: ["#FF6384", "#36A2EB", "#FFCE56"],
            }
        ]
    })

    // Reference to the chart canvas
    const chartCanvas = ref(null)

    // Chart instance
    let chart;

    // Function to create the pie chart
    const createPieChart = () => {
        chart = new Chart(chartCanvas.value, {
            type: "pie",
            data: chartData.value
        })
    };

    // Initialize the pie chart
    onMounted(() => {
        createPieChart();
    });

    onBeforeUnmount(() => {
        // Destroy the chart instance
        if (chart) {
            chart.destroy();
        }
    })
</script>

<template>
    <div class="pie-chart flex justify-center items-center">
      <canvas ref="chartCanvas"></canvas>
    </div>
  </template>
  
 
  <style scoped>
  .pie-chart {
    width: 400px;
    margin: 0 auto;
  }
  @media screen and (max-width: 768px) {
    .pie-chart {
      width: 100%;
      margin: 0 auto;
    }
    
  }
  </style>
  