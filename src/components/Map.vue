<template>
    <div>
      <div id="container"></div>
    </div>
  </template>
  

<script>
import worldMap from '/src/geo.json';

import Highcharts from 'highcharts';
import HighchartsMap from 'highcharts/modules/map';

// Initialize the map module
HighchartsMap(Highcharts);

export default {
    name: 'Map',
    methods: {
        renderHighchartsMap() {
            Highcharts.mapChart('container', {
                chart: {
                    map: worldMap,
                },
                title: {
                    text: 'India',
                },
                // Add other Highcharts options as needed
            });
        },
    },
    mounted() {
        this.renderHighchartsMap();
    },

}

</script>

<style scoped>
  #container {
    background-color: red;
    width: 100%;
    height: 500px; /* Adjust the height as needed */
  }
</style>