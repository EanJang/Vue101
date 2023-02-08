<template>
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
</template>

<script>
    export default {
        name: 'radio-check',
        data() {
            return {
                picked: 'Gender Neutral',
            }
        },
    }
</script>

<style>
.picked-box {
    margin-top: 40px;
    margin-bottom: 55px;
}
.picked-list {
    text-decoration: underline 1px solid #42b983;
    text-underline-offset: 4px;
}
</style>