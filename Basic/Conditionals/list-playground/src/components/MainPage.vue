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
    <p v-else-if="show">Your List is Empty:(</p>
    <h3>Push & Pop</h3>
    <button>PUSH</button>
    <button>POP</button>
    <ul>
      <li v-for="(item, index) of secondList" v-bind:key="index">{{ item }}</li>
    </ul>
    <ul>
      <li><a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank" rel="noopener">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank" rel="noopener">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank" rel="noopener">Twitter</a></li>
      <li><a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a></li>
    </ul>
    <h3>Reverse</h3>
    <ul>
      <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
      <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
      <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools" target="_blank" rel="noopener">vue-devtools</a></li>
      <li><a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">awesome-vue</a></li>
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
      secondList: [1, 2, 3]
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
