<template>
  <div class="counter">
    <h1>{{ title }}</h1>
    <p>
      You've hit {{ hits }} times!
    </p>
    <h3>{{ count }}</h3>
    <div class="button-wrapper">
      <CounterButton symbol="-" />
      <CounterButton symbol="+" />
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
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
</style>
