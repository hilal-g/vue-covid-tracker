<template>
  <div class="barchart">
     <D3BarChart :config="chart_config" :datum="chart_data"></D3BarChart>
  </div>
</template>

<script>
import { D3BarChart } from 'vue-d3-charts';

export default {
  name: 'BarChart',
  components: {
    D3BarChart
  },
  props: {
    chart_data: Array
  },
  data() {
    return {
      chart_config : {
        key: 'Country',
        values: ['Value'],
        color: {current:'#41B882'},
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style> 
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>