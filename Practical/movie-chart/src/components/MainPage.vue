const { default: axios } = require("axios")

<template>
  <div class="main">
    <h1>{{ msg }}</h1>
    <h3>
      Weekend US Box Office Chart for February 17, 2023
    </h3>
    <p>
      Visit  <a href="https://www.the-numbers.com/weekend-box-office-chart" target="_blank">THE NUMBERS</a> web page for more details.
    </p>
    <GridChart
      :data="gridData"
      :columns="gridColumns"
    />
  </div>
</template>

<script>
import GridChart from './GridChart'
const axios = require('axios').default;

export default {
  name: 'MainPage',
  props: {
    msg: String
  },
  components: {
    GridChart
  },
  data() {
    return {
      gridData: [],
      gridColumns: []
    }
  },
  methods: {
    getColumn() {
      axios.get('http://localhost:3000/gridColumns').then((res) => {
        console.log(res.data);
        this.gridColumns.push(...res.data);
      })
    },
    getMovieData() {
      axios.get('http://localhost:3000/gridData').then((res) => {
        console.log(res.data);
        this.gridData.push(...res.data);
      })
    }
  },
  mounted() {
    this.getColumn();
    this.getMovieData();
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
a {
  color: #42b983;
}
.main {
  display: flex;
  flex-direction: column;
}
</style>
