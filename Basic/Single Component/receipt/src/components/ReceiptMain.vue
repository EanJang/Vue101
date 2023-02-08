<template>
<div class="receipt">
<h2 class="name"> Brandname </h2>
<p class="greeting"> Thank you for your order! </p>

<!-- Order info -->
<div class="order">
  <p> Order No : 1234567890 </p>
  <p> Date : 4/5/2020 </p>
  <p> Shipping Address : My sweet home </p>
</div>

<hr>

<!-- Details -->
<div class="details">

  <h3> Details </h3>
  <div class="product">
    <img src="https://www.freeiconspng.com/uploads/aesthetic-chair-png-5.png" alt="">
    <div class="info">
      <h4> Zmerc </h4>
      <p> Color: Mercine </p>
      <p> Qty: 1 </p>
    </div>
  </div>

  <p> 128 &dollar; </p>

</div>

<!-- Sub and total price -->
<div class="totalprice">
  <p class="sub"> Subtotal <span> 128 &dollar; </span></p>
  <p class="del"> Delivery <span> 10 &dollar; </span> </p>
  <hr>
  <p class="tot"> Total <span> 138 &dollar; </span> </p>
</div>

<!-- Footer -->
<footer> Lorem ipsum dolor sit amet consectetur adipisicing. </footer>

</div>
</template>

<script>
export default {
  name: 'ReceiptMain'
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
  height: 720px;
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
  width: 65px;
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
