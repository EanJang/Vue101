<template>

<div v-for="(menu, index) in orderedMenu" :key="index" class="details">
        <h3 v-if="menu.id === 1"> Details </h3>
        <div class="product">
            <img :src="menu.img" alt="{{ menu.alt }}">
            <div class="info">
                <h4> {{ menu.menu }} </h4>
                <p> {{ menu.option }} </p>
                <p> Qty: {{ menu.Qty }} </p>
            </div>
        </div>
        <p> {{ menu.Price }} &dollar; </p>
    </div>

</template>

<script>
    export default {
        name: 'OrderedProduct',
        props: {
            orderedMenu: Array
        },
        data() {
            return {

            }
        }
    }
</script>

<style>
/* Order details */
.details {
    padding-left: 10px;
    margin-bottom: 35px;
    overflow: hidden
}

.details h3 {
    font-weight: 400;
    color: #6c8b8e;
    font-size: 1.5em;
    margin-bottom: 15px
}

/* Image and the info of the order */
.product {
    float: left;
    width: 83%
}

.product img {
    width: 70px;
    height: 70px;
    float: left
}

.product .info {
    float: left;
    margin-left: 15px
}

.product .info h4 {
    color: #6f8d90;
    font-weight: 400;
    text-transform: uppercase;
    margin-top: 10px
}

.product .info p {
    font-size: 12px;
    color: #aaa;
}
</style>