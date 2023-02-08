<template>
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
        <li>{{ selectedTime }}</li>
        </ul>
</template>

<script>
    export default {
        name: 'select-box',
        computed: {
            selectedTime() {
                let time = this.selected;
                if (!time) {
                    return ''
                } else if (time === 'Morning') {
                    return '🌄🛌☕'
                } else if (time === 'Afternoon') {
                    return '🏃☀️'
                } else return '🛌💤😴'
            },
        },
        data() {
            return {
                selected: ''
            }
        }
    }
</script>