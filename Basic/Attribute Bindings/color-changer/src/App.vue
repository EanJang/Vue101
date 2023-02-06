<template>
  <div class="button-wrapper">
    <div class="normal-buttons">
      <ColorButton isNormal=true colorToChange="Red" />
      <ColorButton isNormal=true colorToChange="Green" />
      <ColorButton isNormal=true colorToChange="Blue" />
    </div>
    <div class="toggle-button">
      <ColorButton colorToChange="Black" />
    </div>
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
  flex-direction: column;
}

.normal-buttons {
  display: flex;
  justify-content: space-evenly;
  margin-bottom: 10rem;
}
</style>

