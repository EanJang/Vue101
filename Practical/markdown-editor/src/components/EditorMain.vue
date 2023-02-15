<template>
  <h1>{{ msg }}</h1>
  <div class="editor">
    <textarea class="input" :value="input"></textarea>
    <div class="output" v-html="output"></div>
  </div>
</template>

<script>
import { marked } from 'marked';

export default {
  name: 'EditorMain',
  props: {
    msg: String
  },
  data() {
    return {
      input: '# Hello'
    }
  },
  computed: {
    output() {
      return marked(this.input)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.editor {
  height: 100vh;
  margin: 10px 20px;
  display: flex;
}
.input, .output {
  overflow: auto;
  width: 50%;
  height: 100%;
  box-sizing: border-box;
  padding: 0 20px;
}
.input {
  border: none;
  border-right: 1px solid #42b983;
  resize: none;
  outline: none;
  background-color: #f5f5f5;
  font-size: 14px;
  padding: 20px;
}
code {
  color: #f66;
}
</style>
