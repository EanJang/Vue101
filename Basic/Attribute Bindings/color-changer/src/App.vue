<template>
  <ColorButton color="Red" />
  <ColorButton color="Blue" />
  <ColorButton color="Green" />
</template>

<script>
import ColorButton from './components/ColorButton.vue'

export default {
  name: 'App',
  components: {
    ColorButton
  },
  methods: {

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
