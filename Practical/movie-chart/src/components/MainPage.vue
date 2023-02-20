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
</template>

<script>
export default {
  name: 'MainPage',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
