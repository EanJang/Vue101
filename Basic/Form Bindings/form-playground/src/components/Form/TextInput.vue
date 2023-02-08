<template>
    <h3>Text Input</h3>
        <ul>
            <li><input type="text" v-model="inputText" /></li>
        </ul>
        <ul>
            <li>{{ inputText }}</li>
        </ul>
</template>

<script>
    export default {
        name: 'text-input',
        data() {
            return {
                inputText: ''
            }
        }
    }
</script>

<style scoped>
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
</style>