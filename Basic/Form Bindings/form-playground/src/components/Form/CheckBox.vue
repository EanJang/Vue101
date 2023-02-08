<template>
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
            <li class="checked">{{ isChecked }}</li>
        </ul>
</template>

<script>
export default {
        name: 'check-box',
        computed: {
            isChecked() {
                if (this.checked) {
                    return 'Checked!'
                } else {
                    return ''
                }
            }
        },
        data() {
            return {
                checked: false
            }
        }
    }
</script>