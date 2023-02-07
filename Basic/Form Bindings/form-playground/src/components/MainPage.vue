<template>
  <div class="main">
    <h1>{{ msg }}</h1>
    <p>
      We can create two-way bindings between state and form inputs using the v-model directive!
    </p>
    <h3>Text Input</h3>
    <ul>
      <li>
        <input type="text" v-model="inputText" />
      </li>
    </ul>
    <ul>
      <li class="mirrorText">
        {{ inputText }}
      </li>
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
  },
  data() {
    return {
      inputText: ''
    }
  },
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
input[type=text] {
  font-size: 13px;
  text-align: center;
  border-color: #42b983;
  padding: 8px 10px;
  border-width: 1px;
  border-style: dotted;
}
input[type=text]:focus {
  outline:none;
}
.mirrorText {
  text-decoration: underline 1px solid #42b983;
}
</style>
