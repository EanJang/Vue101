<template>
  <div class="main">
    <h1>{{ msg }}</h1>
    <p>
      We can create two-way bindings between state and form inputs using the v-model directive!
    </p>
    <h3>Text Input</h3>
    <ul>
      <li></li>
    </ul>
    <h3>Checkbox</h3>
    <ul>
      <li></li>
    </ul>
    <h3>Multi Checkbox</h3>
    <ul>
      <li></li>
    </ul>
    <h3>Radio</h3>
    <ul>
      <li></li>
    </ul>
    <h3>Select</h3>
    <ul>
      <li></li>
    </ul>
    <h3>Multi Select</h3>
    <ul>
      <li></li>
    </ul>
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
