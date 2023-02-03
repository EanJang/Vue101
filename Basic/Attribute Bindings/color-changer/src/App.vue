<template>
  <div class="button-wrapper">
    <ColorButton colorToChange="Red" />
    <ColorButton colorToChange="Green" />
    <ColorButton colorToChange="Blue" />
  </div>
</template>

<script>
import ColorButton from './components/ColorButton.vue'

export default {
  name: 'App',
  components: {
    ColorButton
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

.button-wrapper {
  display: flex;
  justify-content: space-evenly;
}
</style>

