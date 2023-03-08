<template>
  <div class="cart__contents-section">
    <div class="cart-item__contents">
      <div class="cart-item-img">
        <img src="../assets/sneakers_blue-bg.png" alt="" class="item-img">
        <p class="cart-item-quantity">1</p>
      </div>
      <div class="item-details-about">
        <span class="cart-item-title">Nike sneakers</span>
        <span class="cart-item-price">$120.90</span>
      </div>
     
    </div>

    <div class="cart-item__contents">
      <div class="cart-item-img">
        <img src="../assets/sneakers_green-bg.png" alt="" class="item-img">
        <p class="cart-item-quantity">1</p>
      </div>
      <div class="item-details-about">
        <span class="cart-item-title">Nike sneakers</span>
        <span class="cart-item-price">$120.90</span>
      </div>
    </div>

    <div class="cart-item__contents">
      <div class="cart-item-img">
        <img src="../assets/sneakers_pink-bg.png" alt="" class="item-img">
        <p class="cart-item-quantity">1</p>
      </div>
      <div class="item-details-about">
        <span class="cart-item-title">Nike sneakers</span>
        <span class="cart-item-price">$120.90</span>
      </div>
    </div>
  </div>

  <div class="subtotal__sum-and-shipping">
    <div class="subtotal__sum">
      <span class="subtotal__sum-text">Subtotal:</span>
      <span class="subtotal__sum-sum">$362.70</span>
    </div>

    <div class="subtotal__sum">
      <span class="shipping__sum-text">Shipping:</span>
      <span class="shipping__sum-sum">Free</span>
    </div>
  </div>

  <div class="total__sum">
    <span class="total__sum-text">Total</span>
    <span class="total__sum-sum">$362.70</span>
  </div>

  <div class="safe__payment-about">
    <div class="secure__ssl">
      <img src="../assets/secure-img.svg" alt="" class="secure-img">
      <span class="secure-text">Secure SSL Encryption & Guaranteed Safe Checkout</span>
    </div>

    <div class="payment__group">
      <img src="../assets/payment-group.png" alt="">
    </div>
  </div>

  <div class="jewellery__club-about">
    <span class="jewellery__club-headline">The ultimate jewellery club</span>
    <span class="jewellery__club-description">Ornare rhoncus nunc ut felis. Faucibus dolor at ultrices tincidunt. Pulvinar sed justo et viverra pellentesque.</span>

    <div class="jewellery__club-advances">
      <div class="list__of__advnces">
        <img src="../assets/ok__sign.svg" alt="">
        <span>Extra 10$ off!</span>
      </div>
      <div class="list__of__advnces">
        <img src="../assets/ok__sign.svg" alt="">
        <span>Free shipping on marked club items!</span>
      </div>
      <div class="list__of__advnces">
        <img src="../assets/ok__sign.svg" alt="">
        <span>Free returns on marked club items!</span>
      </div>
    </div>
  </div>
</template>
<style scoped>
.cart__contents-section{
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 16px;
}
.cart__contents-section::after{
  content: '';
  height: 1px;
  background: #D6D8EE;
  width: 100%;
}
.cart-item__contents{
  display: grid;
  align-items: center;
  grid-template-columns: 0.2fr 1fr;
  grid-column-gap: 14px;
}
.item-details-about{
  display: flex;
  justify-content: space-between;
  font-weight: 400;
  font-size: 16px;
  line-height: 26px;
  color: var(--primary--dark);
}
.cart-item-img{
  display: flex;
  position: relative;
}
.cart-item-quantity{
  background: #4B4E68;
  width: 18px;
  height: 18px;
  border: none;
  border-radius: 50%;
  color: white;
  position: absolute;
  display: flex;
  justify-content: center;
  top: -5px;
  right: -4px;
}
.subtotal__sum-and-shipping{
  display: flex;
  flex-direction: column;
  margin-top: 16px;
  gap: 11px;
}
.subtotal__sum-and-shipping::after{
  content: '';
  height: 1px;
  background: #D6D8EE;
  width: 100%;
}
.subtotal__sum{
  display: flex;
  justify-content: space-between;
  font-weight: 400;
  font-size: 16px;
  line-height: 26px;
  color: var(--primary--dark);
}
.total__sum{
  margin-top: 16px;
  display: flex;
  justify-content: space-between;
  font-weight: 600;
  font-size: 16px;
  line-height: 26px;
  color: var(--primary--dark);
}
.safe__payment-about{
  margin-top: 40px;
  background: #FFFFFF;
  border: 1px solid #D6D8EA;
  border-radius: 32px;
  height: 101px;
  width: 449px;
  align-items: center;
  display: flex;
  flex-direction: column;
  gap: 12px;
}
.secure__ssl{
  padding-top: 22px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 7px;
  font-weight: 400;
  font-size: 14px;
  line-height: 21px;
  color: #4B4E68;
}
.jewellery__club-about{
  width: 449px;
  height: 245px;
  background: #FFFFFF;
  border: 1px solid #D6D8EA;
  border-radius: 32px;
  display: flex;
  flex-direction: column;
  margin-top: 15px;
  padding-left: 30px;
  padding-top: 30px;
}
.jewellery__club-headline{
  font-weight: 600;
  font-size: 18px;
  line-height: 27px;
  color: var(--primary--dark);
}
.jewellery__club-description{
  font-weight: 400;
  font-size: 14px;
  line-height: 24px;
  color: #4B4E68;
  padding-top: 10px;
}
.jewellery__club-advances{
  padding-top: 20px;
  display: flex;
  flex-direction: column;
  gap: 4px;
}
.list__of__advnces{
  display: flex;
  gap: 10px;
  align-items: center;
  font-weight: 400;
  font-size: 14px;
  line-height: 24px;
  color: #4B4E68;
}

</style>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'Cart',
  
})
</script>
