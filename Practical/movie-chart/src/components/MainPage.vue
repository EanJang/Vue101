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
          'Movie Title': 'Ant-Man and the Wasp: Quantumania',
          'Director': 'Peyton Reed',
          'Distributor': 'Walt Disney',
          'Gross': 104000000,
          'Total Gross': 104000000
        },
        {
          'Movie Title': 'Avatar: The Way of Water',
          'Director': 'James Cameron',
          'Distributor': '20th Century Studios',
          'Gross': 6118000,
          'Total Gross': 657075991
        },
        {
          'Movie Title': "Magic Mike’s Last Dance",
          'Director': 'Steven Soderbergh',
          'Distributor': 'Warner Bros',
          'Gross': 5525000,
          'Total Gross': 18115454
        },
        {
          'Movie Title': 'Puss in Boots: The Last Wish',
          'Director': 'Joel Crawford',
          'Distributor': 'Universal',
          'Gross': 5260000,
          'Total Gross': 166076100
        },
        {
          'Movie Title': 'Knock at the Cabin',
          'Director': 'M. Night Shyamalan',
          'Distributor': 'Universal',
          'Gross': 3900000,
          'Total Gross': 30372270
        },
        {
          'Movie Title': '80 for Brady',
          'Director': 'Kyle Marvin',
          'Distributor': 'Paramount Pictures',
          'Gross': 3600000,
          'Total Gross': 32248000
        },
        {
          'Movie Title': 'Titanic (25th Anniversary)',
          'Director': 'James Cameron',
          'Distributor': 'Paramount Pictures',
          'Gross': 2290000,
          'Total Gross': 671776000
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
.main {
  display: flex;
  flex-direction: column;
}
</style>
