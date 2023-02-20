<template>
  <div class="main">
    <h1>{{ msg }}</h1>
    <h3>
      Weekend US Box Office Chart for February 17, 2023
    </h3>
    <p>
      Visit  <a href="https://www.the-numbers.com/weekend-box-office-chart" target="_blank">THE NUMBERS</a> web page for more details.
    </p>
  </div>
  <div>
    <GridChart
      :data="gridData"
      :columns="gridColumns"
    />
  </div>
</template>

<script>
import GridChart from './GridChart'

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
      gridColumns: ['Movie Title', 'Director', 'Distributor', 'Gross', 'Total Gross'],
      gridData:[
        {
          movieTitle: 'Ant-Man and the Wasp: Quantumania',
          director: 'tmp',
          distributor: 'Walt Disney',
          gross: 104000000,
          totalGross: 104000000
        },
        {
          movieTitle: 'Avatar: The Way of Water',
          director: 'tmp',
          distributor: '20th Century Studios',
          gross: 6118000,
          totalGross: 657075991
        },
        {
          movieTitle: "Magic Mike’s Last Dance",
          director: 'tmp',
          distributor: 'Warner Bros',
          gross: 5525000,
          totalGross: 18115454
        },
        {
          movieTitle: 'Puss in Boots: The Last Wish',
          director: 'tmp',
          distributor: 'Universal',
          gross: 5260000,
          totalGross: 166076100
        },
        {
          movieTitle: 'Knock at the Cabin',
          director: 'tmp',
          distributor: 'Universal',
          gross: 3900000,
          totalGross: 30372270
        },
        {
          movieTitle: '80 for Brady',
          director: 'tmp',
          distributor: 'Paramount Pictures',
          gross: 3600000,
          totalGross: 32248000
        },
        {
          movieTitle: 'Titanic (25th Anniversary)',
          director: 'tmp',
          distributor: 'Paramount Pictures',
          gross: 2290000,
          totalGross: 671776000
        },
      ]
    }
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
</style>
