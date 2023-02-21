<template>
    <table>
        <thead>
            <tr v-for="column in columns" :key="column">
                <th>
                    {{ column }}
                </th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>
                </td>
            </tr>
        </tbody>
    </table>
</template>

<script>
export default {
    name: 'GridChart',
    props: {
        data: Array,
        columns: Array
    },
    mounted() {
        console.log(this.data);
    }
}
</script>

<style scoped>
table {
    border: 2px solid #42b983;
    border-radius: 3px;
    background-color: #fff;
}
th {
    background-color: #42b983;
    color: rgba(255, 255, 255, 0.66);
    cursor: pointer;
    user-select: none;
}
td {
    background-color: #f9f9f9;
}
th,
td {
    min-width: 120px;
    padding: 10px 20px;
}
</style>
