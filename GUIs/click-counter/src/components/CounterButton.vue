<template>
    <div>
        <button>{{ symbol }}</button>
    </div>
</template>

<script>
export default {
    name: 'CounterButton',
    props: {
        symbol: String
    },
    data() {
        return {

        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
