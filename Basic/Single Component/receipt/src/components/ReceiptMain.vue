<template>
<div class="receipt">
<h2 class="name"> GREENWICH </h2>
<p class="greeting"> Thank you for your order! </p>

<!-- Order info -->
<div class="order">
  <p> Order No : 20201228LEO </p>
  <p> Date : 09/02/2023 </p>
  <p> Serve Option : Delivery </p>
</div>

<hr>

<!-- Details -->
<OrderedProduct />

<!-- Sub and total price -->
<div class="totalprice">
  <p class="sub"> Subtotal <span> 23 &dollar; </span></p>
  <p class="del"> Delivery <span> 5 &dollar; </span> </p>
  <hr>
  <p class="tot"> Total <span> 28 &dollar; </span> </p>
</div>

<!-- Footer -->
<footer> Happy Meal for your Happy Day! </footer>

</div>
</template>

<script>
import OrderedProduct from './OrderedProduct'

export default {
  name: 'receipt-main',
  components: {
    OrderedProduct
  }
}
</script>


<style>
/* Our Font */
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;700&display=swap');

/* Global */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Poppins'
}

body {
  height: 100vh;
  background-color: #D3E1E1
}

/* The Receipt */
.receipt {
  width: 360px;
  height: 800px;
  background-color: white;
  border-radius: 30px;
  position: relative;
  top: 50%;
  left: 50%;
  margin-top: 150px; /* -half height and width to center */
  margin-left: -180px;
  box-shadow: 14px 14px 22px -18px;
  padding: 20px
}

/* Heading */
.name {
  text-transform: uppercase;
  text-align: center;
  color: #6c8b8e;
  letter-spacing: 10px;
  font-size: 1.8em;
  margin-top: 10px
}

/* Big thank */
.greeting {
  font-size: 21px;
  text-transform: capitalize;
  text-align: center;
  color: #6f8d90;
  margin: 35px 0;
  letter-spacing: 1.2px
}

/* Order info */
.order p {
  font-size: 13px;
  color: #aaa;
  padding-left: 10px;
  letter-spacing: .7px
}

/* Our line */
hr {
  border: .7px solid #ddd;
  margin: 15px 0;
}

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

/* Net price */
.details > p {
  color: #6f8d90;
  margin-top: 25px;
  font-size: 15px
}

/* Total price */
.totalprice {
  margin-top: 40px;
}

.totalprice p {
  padding-left: 10px
}

.totalprice .sub,
.totalprice .del {
  font-size: 13px;
  color: #aaa
}

.totalprice span {
  float: right;
  margin-right: 17px
}

.totalprice .tot {
  color: #6f8d90;
  font-size: 15px
}

/* Footer */
footer {
  font-size: 10px;
  text-align: center;
  margin-top: 135px;
  color: #aaa
}
</style>
