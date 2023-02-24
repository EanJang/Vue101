<template>
    <div class="table-wrapper">
        <table v-if=data>
            <thead>
                <tr>
                    <th v-for="(column, index) in columns" :key="index">
                        {{ column }}
                    </th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="movie in data" :key="movie">
                    <td v-for="column in columns" :key="column">
                        {{ movie[column] }}
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    name: 'GridChart',
    props: {
        data: Array,
        columns: Array
    },
    mounted() {
    }
}
</script>

<style scoped>
.table-wrapper {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 35px;
}
table {
    width: 85%;
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
