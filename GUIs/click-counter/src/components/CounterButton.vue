<template>
    <div>
        <button @click="triggerCount">{{ symbol }}</button>
    </div>
</template>

<script>
export default {
    name: 'CounterButton',
    props: {
        symbol: String
    },
    methods: {
        triggerCount() {
            console.log(this.symbol);
            if (this.symbol === "+") {
                console.log('+');
            } else {
                console.log('-');
            }
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
button {
    width: 110px;
    height: 40px;
    border: none;
    border-radius: 5px;
    margin: 10px 40px;
    color: lightgrey;
    font-size: 20px;
    background-color: #34495e;
}
button:hover{
    cursor: pointer;
    background-color: #42b983;
}
</style>
