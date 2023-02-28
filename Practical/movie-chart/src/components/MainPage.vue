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
    <div class="chart-box">
      <input class="search-bar" v-model="searchQuery" />
      <GridChart
        :data="gridData"
        :columns="gridColumns"
        :searchKey="searchQuery"
      />
    </div>
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
      searchQuery: '',
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
  align-items: center;
}
.chart-box {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 35px;
}
.search-bar {
  width: 25%;
  margin-left: auto;
  padding: 8px 5px;
  background-image: url("data:image/svg+xml;charset=utf8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24'%3E%3Cpath d='M15.5 14h-.79l-.28-.27C15.41 12.59 16 11.11 16 9.5 16 5.91 13.09 3 9.5 3S3 5.91 3 9.5 5.91 16 9.5 16c1.61 0 3.09-.59 4.23-1.57l.27.28v.79l5 4.99L20.49 19l-4.99-5zm-6 0C7.01 14 5 11.99 5 9.5S7.01 5 9.5 5 14 7.01 14 9.5 11.99 14 9.5 14z'/%3E%3Cpath d='M0 0h24v24H0z' fill='none'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-size: 18px 18px;
  background-position: 95% center;
  border: 1px solid #42b983;
  transition: all 250ms ease-in-out;
  backface-visibility: hidden;
  transform-style: preserve-3d;
}
.search-bar:hover, .search-bar:focus {
  outline: 0;
  border: 1px solid transparent;
  border-bottom: 1px solid #42b983;
  border-radius: 0;
  background-position: 100% center;
}
</style>
