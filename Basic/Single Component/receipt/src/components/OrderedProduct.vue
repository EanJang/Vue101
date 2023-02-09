<template>
    <div class="details">
        <h3> Details </h3>
        <div class="product">
            <img src="https://www.freeiconspng.com/uploads/lunch-panini-sandwiches-25.png" alt="">
            <div class="info">
                <h4> Panini Sandwich </h4>
                <p> Tomato & Mozzarella </p>
                <p> Qty: 1 </p>
            </div>
        </div>
        <p> 9 &dollar; </p>
    </div>

    <div class="details">
        <div class="product">
            <img src="https://www.freeiconspng.com/uploads/lunch-png-8.png" alt="">
            <div class="info">
                <h4> Fresh Lunch Set </h4>
                <p> Turkey Bacon </p>
                <p> Qty: 1 </p>
            </div>
        </div>
        <p> 14 &dollar; </p>
    </div>
</template>

<script>
    export default {
        name: 'OrderedProduct'
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