<template>
  <div class="main">
    <h1>{{ msg }}</h1>
    <p>
      We can create two-way bindings between state and form inputs using the v-model directive!
    </p>
    <h3>Text Input</h3>
    <ul>
      <li>
        <input type="text" v-model="inputText" />
      </li>
    </ul>
    <ul>
      <li>
        {{ inputText }}
      </li>
    </ul>
    <h3>Checkbox</h3>
    <ul>
      <li>
        <label class="control control-checkbox">
          Checkbox
          <input type="checkbox" v-model="checked" />
          <div class="control_indicator"></div>
        </label>
      </li>
    </ul>
    <ul>
      <li class="checked">
        {{ isChecked }}
      </li>
    </ul>
    <h3>Multi Checkbox</h3>
    <ul>
      <li>
        <label class="control control-checkbox" for="multi1">
          Cheese🧀
          <input type="checkbox" id="multi1" value="🧀" v-model="multiChecked" />
          <div class="control_indicator"></div>
        </label>
      </li>
      <li>
        <label class="control control-checkbox" for="multi2">
          Chocolate🍫
          <input type="checkbox" id="multi2" value="🍫" v-model="multiChecked" />
          <div class="control_indicator"></div>
        </label>
      </li>
      <li>
        <label class="control control-checkbox" for="multi3">
          Cake🍰
          <input type="checkbox" id="multi3" value="🍰" v-model="multiChecked" />
          <div class="control_indicator"></div>
        </label>
      </li>
      <li>
        <label class="control control-checkbox" for="multi4">
          Caffè Latte☕
          <input type="checkbox" id="multi4" value="☕" v-model="multiChecked" />
          <div class="control_indicator"></div>
        </label>
      </li>
    </ul>
    <ul class="order-box">
      <p>I will order:</p>
      <p class="order-list">{{ orderedList }}</p>
    </ul>
    <h3>Radio</h3>
    <ul>
      <li>
        <label class="control control-radio" for="radio1">
          Female
          <input type="radio" id="radio1" value="Female" v-model="picked" />
          <div class="control_indicator"></div>
        </label>
      </li>
      <li>
        <label class="control control-radio" for="radio2">
          Male
          <input type="radio" id="radio2" value="Male" v-model="picked" />
          <div class="control_indicator"></div>
        </label>
      </li>
      <li>
        <label class="control control-radio" for="radio3">
          Gender Neutral
          <input type="radio" id="radio3" value="Gender Neutral" v-model="picked" />
          <div class="control_indicator"></div>
        </label>
      </li>
    </ul>
    <ul class="picked-box">
      <p>I am:</p>
      <p class="picked-list">{{ picked }}</p>
    </ul>
    <h3>Select</h3>
    <ul>
      <li>
        <select v-model="selected">
          <option disabled value="">Please select your time</option>
          <option>Morning</option>
          <option>Afternoon</option>
          <option>Night</option>
        </select>
      </li>
    </ul>
    <ul>
      <li>
        {{ selectedTime }}
      </li>
    </ul>
    <h3>Multi Select</h3>
    <ul>
      <li>
        <select multiple>
          <option disabled value="">Choose your MBTI</option>
          <option>INTJ</option>
          <option>INFJ</option>
          <option>ISTJ</option>
          <option>ISTP</option>
        </select>
      </li>
      <li>Your are...</li>
    </ul>

  </div>
</template>

<script>
export default {
  name: 'MainPage',
  props: {
    msg: String
  },
  computed: {
    isChecked() {
      if (this.checked) {
        return 'Checked!'
      } else {
        return ''
      }
    },
    orderedList() {
      const list = this.multiChecked.toString().replaceAll(",", " "); //remove bracket from array, and replace comma with blank
      return list;
    },
    selectedTime() {
      let time = this.selected;
      if (!time) {
        return ''
      } else if (time === 'Morning') {
        return '🌄🛌☕'
      } else if (time === 'Afternoon') {
        return '🏃☀️'
      } else return '🛌💤😴'
    }
  },
  data() {
    return {
      inputText: '',
      checked: false,
      multiChecked: [],
      picked: 'Gender Neutral',
      selected: ''
    }
  },
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
input[type=text] {
  font-size: 13px;
  text-align: center;
  border-color: #42b983;
  padding: 8px 10px;
  border-width: 1px;
  border-style: dotted;
}
input[type=text]:focus {
  outline:none;
}
.control {
    display: block;
    position: relative;
    padding-left: 30px;
    margin-bottom: 4px;
    padding-top: 2px;
    cursor: pointer;
    font-size: 14px;
}
.control input {
  position: absolute;
  z-index: -1;
  opacity: 0;
}
.control_indicator {
  position: absolute;
  top: 1px;
  left: 0;
  height: 20px;
  width: 20px;
  background: #e6e6e6;
  border: 0px solid #000000;
  border-radius: 0px;
}
.control:hover input ~ .control_indicator,
.control input:focus ~ .control_indicator {
    background: #cccccc;
}

.control input:checked ~ .control_indicator {
    background: #42b983;
}
.control:hover input:not([disabled]):checked ~ .control_indicator,
.control input:checked:focus ~ .control_indicator {
    background: #0e6647d;
}
.control_indicator:after {
    box-sizing: unset;
    content: '';
    position: absolute;
    display: none;
}
.control input:checked ~ .control_indicator:after {
    display: block;
}
.control-checkbox .control_indicator:after {
    left: 8px;
    top: 4px;
    width: 3px;
    height: 8px;
    border: solid #ffffff;
    border-width: 0 2px 2px 0;
    transform: rotate(45deg);
}
.control-checkbox .control_indicator::before {
    content: '';
    display: block;
    position: absolute;
    left: 0;
    top: 0;
    width: 4.5rem;
    height: 4.5rem;
    margin-left: -1.3rem;
    margin-top: -1.3rem;
    background: #42b983;
    border-radius: 3rem;
    opacity: 0.6;
    z-index: 99999;
    transform: scale(0);
}
.control-radio .control_indicator {
    border-radius: 50%;
}

.control-radio .control_indicator:after {
    left: 7px;
    top: 7px;
    height: 6px;
    width: 6px;
    border-radius: 50%;
    background: #ffffff;
    transition: background 250ms;
}
.control-radio input:disabled ~ .control_indicator:after {
    background: #7b7b7b;
}.control-radio .control_indicator::before {
    content: '';
    display: block;
    position: absolute;
    left: 0;
    top: 0;
    width: 4.5rem;
    height: 4.5rem;
    margin-left: -1.3rem;
    margin-top: -1.3rem;
    background: #2aa1c0;
    border-radius: 3rem;
    opacity: 0.6;
    z-index: 99999;
    transform: scale(0);
}
@keyframes s-ripple {
    0% {
        transform: scale(0);
    }
    20% {
        transform: scale(1);
    }
    100% {
        opacity: 0;
        transform: scale(1);
    }
}
@keyframes s-ripple-dup {
    0% {
        transform: scale(0);
    }
    30% {
        transform: scale(1);
    }
    60% {
        transform: scale(1);
    }
    100% {
        opacity: 0;
        transform: scale(1);
    }
}
@keyframes s-ripple {
    0% {
        opacity: 0;
        transform: scale(0);
    }
    20% {
        transform: scale(1);
    }
    100% {
        opacity: 0.01;
        transform: scale(1);
    }
}
@keyframes s-ripple-dup {
    0% {
        transform: scale(0);
    }
    30% {
        transform: scale(1);
    }
    60% {
        transform: scale(1);
    }
    100% {
        opacity: 0;
        transform: scale(1);
    }
}
.control-checkbox input + .control_indicator::before {
    animation: s-ripple 250ms ease-out;
}
.control-checkbox input:checked + .control_indicator::before {
    animation-name: s-ripple-dup;
}
.control-radio input + .control_indicator::before {
    animation: s-ripple 250ms ease-out;
}
.control-radio input:checked + .control_indicator::before {
    animation-name: s-ripple-dup;
}
.checked {
  text-decoration: underline 1px solid #42b983;
}
.order-box {
  margin-top: 40px;
  margin-bottom: 55px;
}
.order-list {
  text-decoration: underline 1px solid black;
  text-underline-offset: 4px;
}
select {
  font-size: 13px;
  text-align: center;
  border-color: #42b983;
  padding: 4px 10px;
  border-width: 1px;
  border-style: dotted;
}
select:focus {
  outline:none;
}
.picked-box {
  margin-top: 40px;
  margin-bottom: 55px;
}
.picked-list {
  text-decoration: underline 1px solid #42b983;
  text-underline-offset: 4px;
}
</style>
