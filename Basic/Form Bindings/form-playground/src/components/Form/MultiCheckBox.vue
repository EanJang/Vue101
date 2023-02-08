<template>
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
</template>

<script>
    export default {
        name: 'multi-check-box',
        computed: {
            orderedList() {
                const list = this.multiChecked.toString().replaceAll(",", " "); //remove bracket from array, and replace comma with blank
                return list;
            }
        },
        data() {
            return {
                multiChecked: []
            }
        },
    }
</script>

<style>
.order-box {
    margin-top: 40px;
    margin-bottom: 55px;
}
.order-list {
    text-decoration: underline 1px solid black;
    text-underline-offset: 4px;
}
</style>