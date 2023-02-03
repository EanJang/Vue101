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
  button {
    font-weight: 0;
    font-size: 20px;
    color: #000000;
    background-color: #ffffff;
    padding: 5px 50px;
    border: solid #000000 2px;
    box-shadow: rgba(0, 0, 0, 0.15) 0px 2px 8px;
    border-radius: 1px;
    transition : 1000ms;
    transform: translateY(0);
    text-transform: uppercase;
  }

  button:hover {
    transition : 1000ms;
    padding: 10px 44px;
    transform : translateY(-0px);
    background-color: #000000;
    color: #ffffff;
    border: solid 2px #ffffff;
  }
</style>