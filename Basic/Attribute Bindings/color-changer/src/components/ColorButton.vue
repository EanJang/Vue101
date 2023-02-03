<template>
    <button :style="{color: currentColor}" @click="changeColor">Turn me {{ colorToChange }}</button>
</template>

<script>
export default {
  name: 'ColorButton',
  props: {
    colorToChange: String
  },
  data() {
    return {
      currentColor: 'black'
    }
  },
  methods: {
    changeColor() {
      this.currentColor = this.colorToChange;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
