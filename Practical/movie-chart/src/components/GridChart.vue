<template>
    <div class="table-wrapper">
        <table v-if=filteredData>
            <thead>
                <tr>
                    <th v-for="(column, index) in columns" :key="index">
                        {{ column }}
                    </th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="movie in filteredData" :key="movie">
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
        columns: Array,
        searchKey: String
    },
    computed: {
        filteredData() {
            const key = this.searchKey.toLowerCase().trim();
            let data = this.data;
            if (key) {
                data = data.filter((row) => {
                        return Object.keys(row).some((k) => {
                        return String(row[k]).toLowerCase().indexOf(key) > -1
                    })
                })
            }
            return data;
        }
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
    width: 1080px;
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
