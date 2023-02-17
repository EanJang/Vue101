<template>
  <div class="counter">
    <h1>{{ title }}</h1>
    <p>
      You've hit {{ hits }} times!
    </p>
    <h2>SUM</h2>
    <h3>{{ count }}</h3>
    <div class="button-wrapper">
        <CounterButton symbol="-" />
        <CounterButton @incrementCount="increment" symbol="+" />
    </div>
  </div>
</template>

<script>
import CounterButton from './CounterButton'

export default {
  name: 'ClickCounter',
  props: {
    title: String
  },
  components: {
    CounterButton
  },
  data() {
    return {
      hits: 0,
      count: 0
    }
  },
  methods: {
    increment() {
      this.count++;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
body {
  display: flex;
}
h2{
  margin: 80px 0 -15px 0;
}
h3 {
  margin: 40px 0;
}
.button-wrapper{
  display: flex;
  justify-content: center;
  width: 100%;
}
</style>
