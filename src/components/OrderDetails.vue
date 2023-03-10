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
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: ' OrderDetails',
  data (){
    return {
      mobile: true,
    }
  }
})
</script>

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
</style>