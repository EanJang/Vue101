<template>
  <div class="main">
    <h1>{{ msg }}</h1>
    <p>
      Toggle, Push & Pop, and Reverse Your List!
    </p>
    <h3>Show & Hide</h3>
    <button v-if="firstList.length" v-on:click="show = !show">{{ showOrHide }}</button>
    <ul v-if="show && firstList.length">
      <li v-for="(item, index) of firstList" v-bind:key="index">{{ item }}</li>
    </ul>
    <h3>Push & Pop</h3>
    <button v-on:click="secondList.push(secondList.length + 1)">PUSH</button>
    <button v-on:click="secondList.pop()">POP</button>
    <ul v-if="secondList.length">
      <li v-for="(item, index) of secondList" v-bind:key="index">{{ item }}</li>
    </ul>
    <ul v-else>
      <li>Your List is Empty:(</li>
    </ul>
    <h3>Reverse</h3>
    <button v-on:click="thirdList.reverse()">PHASE of the MOON</button>
      <ul>
        <li v-for="(item, index) of thirdList" v-bind:key="index">{{ item }}</li>
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
      show: true,
      firstList: ['apple🍎', 'banana🍌', 'cherry🍒'],
      secondList: [1, 2, 3],
      thirdList: ['🌒', '🌓', '🌔', '🌕', '🌖', '🌗', '🌘']
    }
  },
  computed: {
    showOrHide() {
      return this.show ? 'HIDE' : 'SHOW';
    }
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
button {
  background: none;
  border: none;
  text-decoration: underline 1px solid #42b983;
  color: #42b983;
  cursor: pointer;
  margin: 30px 0 5px 0;
}
button:nth-child(2) {
  margin-left: 10px;
}
</style>
