<template>
    <h3>Multi Select</h3>
        <ul>
        <li>
            <select multiple v-model="multiSelected">
                <option disabled value="">Choose your MBTI</option>
                <option>INTJ</option>
                <option>INFJ</option>
                <option>ISTJ</option>
                <option>ISTP</option>
            </select>
        </li>
        </ul>
        <ul>
            <li>Your are <span class="personality">{{ personalityType }}</span></li>
        </ul>
</template>

<script>
    export default {
        name: 'multi-select-box',
        computed: {
            personalityType() {
                let personality = this.multiSelected.toString();
                switch(personality) {
                    case "INTJ":
                        return "an Architect!";
                    case "INFJ":
                        return "an Advocate!";
                    case "ISTJ":
                        return "a Logistician!";
                    case "ISTP":
                        return "a Virtuso!";
                    default:
                        return "unpredictable...";
                }
            }
        },
        data() {
            return {
                multiSelected: ''
            }
        }
    }
</script>

<style>
.personality {
    color: #42b983;
}
</style>