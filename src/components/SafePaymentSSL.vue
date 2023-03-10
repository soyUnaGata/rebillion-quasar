<template>
    <div class="safe__payment-about">
        <div class="secure__ssl">
        <img src="../assets/secure-img.svg" alt="" class="secure-img">
        <span class="secure-text">Secure SSL Encryption & Guaranteed Safe Checkout</span>
        </div>

      
        <div class="payment__group-section">
          <img src="../assets/secure-section-img-1.png" alt="">
          <img src="../assets/secure-section-img-2.png" alt="">
          <img src="../assets/secure-section-img-3.png" alt="">
          <img src="../assets/secure-section-img-4.png" alt="">
          <img src="../assets/secure-section-img-5.png" alt="">
          <img src="../assets/secure-section-img-6.png" alt="">
        </div>
        
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'SafePaymentSSL'
})
</script>

<style scoped>
.safe__payment-about{
  margin-top: 40px;
  background: #FFFFFF;
  border: 1px solid #D6D8EA;
  border-radius: 32px;
  height: 101px;
  align-items: center;
  display: flex;
  flex-direction: column;
  gap: 12px;
  padding: 22px 30px;
}
.secure__ssl{
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 7px;
  font-weight: 400;
  font-size: 14px;
  line-height: 21px;
  color: #4B4E68;
}
.payment__group-section{
    display: flex;
    gap: 15px;
  }
</style>