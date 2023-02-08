<template>
  <div class="main">
    <h1>{{ msg }}</h1>
    <p>
      We can create two-way bindings between state and form inputs using the v-model directive!
    </p>
    <br />
    <TextInput />
    <CheckBox />
    <MultiCheckBox />
    <RadioCheck />
    <SelectBox />
    <MultiSelectBox />
  </div>
</template>

<script>
import TextInput from './Form/TextInput'
import CheckBox from './Form/CheckBox'
import MultiCheckBox from './Form/MultiCheckBox'
import RadioCheck from './Form/RadioCheck'
import SelectBox from './Form/SelectBox'
import MultiSelectBox from './Form/MultiSelectBox'

export default {
  name: 'MainPage',
  components: {
    TextInput,
    CheckBox,
    MultiCheckBox,
    RadioCheck,
    SelectBox,
    MultiSelectBox
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
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
</style>
