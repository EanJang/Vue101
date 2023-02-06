<template>
    <button v-if="isNormal" :style="{color: currentColor}" @click="changeColor"><span>{{ message }}</span> {{ colorToChange }}</button>
    <button v-else :class="{rainbow: isToggle}" @click="toggleRainbow"><span>{{ message }}</span> {{ colorToChange }} <span v-if="this.isChanged">anymore</span> </button>
</template>

<script>
export default {
  name: 'ColorButton',
  props: {
    colorToChange: String,
    isNormal: Boolean
  },
  data() {
    return {
      currentColor: 'black',
      isChanged: false,
      isToggle: false
    }
  },
  computed: {
    message() {
      if (this.isNormal) {
        return this.isChanged ? 'I am' : 'Turn me'
      } else {
        return this.isChanged ? 'I am not' : 'Now I am'
      }
    }
  },
  methods: {
    toggleRainbow() {
      this.isToggle = !this.isToggle;
      this.isChanged = !this.isChanged;
    },
    changeColor() {
      this.currentColor = this.colorToChange;
      this.isChanged = !this.isChanged;
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

  .rainbow {
    background-image: linear-gradient(to left, violet, indigo, blue, green, yellow, orange, red);
    color: white;
  }
</style>