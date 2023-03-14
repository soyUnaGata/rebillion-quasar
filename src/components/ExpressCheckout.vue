<template>
  <div class="express__checkout">
    <p class="express__checkout-text">Express Checkout</p>
    <div class="payment_type">
      <div class="shop__pay">
        <img src="../assets/shop_pay.png" alt="ShopPay">
      </div>
      <div class="pay__pal">
        <img src="../assets/paypal.svg" alt="PayPal">
      </div>
      <div class="gpay">
        <img src="../assets/gpay.svg" alt="GPay">
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'ExpressCheckout'
})
</script>


<style scoped>
.express__checkout{
  padding: 30px;
  width: 540px;
  max-height: 100%;
  border: 1px solid #D6D8EE;
  border-radius: 32px;
  margin-top: 30px;
  max-width: 100%;
}
.express__checkout-text{
  font-weight: 600;
  font-size: 20px;
  line-height: 30px;
}
.payment_type{
  display: flex;
  gap: 20px;
  align-items: center;
}
.shop__pay,.pay__pal,.gpay{
  width: 147px;
  max-width: 100%;
  height: 50px;
  cursor: pointer;
}
.shop__pay{
  background: rgba(90, 49, 244, 0.1);
  border: 1px solid rgba(90, 49, 244, 0.6);
  border-radius: 16px;
}
.shop__pay, .pay__pal > img {
  padding-top: 15px;
  padding-left: 31px;
}
.pay__pal{
  background: rgba(17, 57, 132, 0.1);
  border: 1px solid rgba(17, 57, 132, 0.6);
  border-radius: 16px;
}
.gpay{
  background: rgba(234, 64, 50, 0.1);
  border: 1px solid rgba(234, 64, 50, 0.6);
  border-radius: 16px;

}
.gpay > img {
  padding-top: 15px;
  padding-left: 48px;
}

</style>