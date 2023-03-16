<template>
  <div class="thank-you-page__wrapper">
    <div class="row">
      <div class="col-12 col-md-6 thanks-part"> 
        <div class="isMobile" >
              <OrderDetailsCollapseable v-if="isTableOrMobile" />
            </div> 
          <div class="thanks-part-inner-wrapper">
            <div class="thanks__for__order">
              <img src="../assets/like.png" alt="">
              <div class="thanks-text">
                <h2 class="thank-you-headling">Thank you for your order</h2>
                <h4 class="thank-you-subheadling">Your order is confirmed</h4>
              </div>
            </div>
            <div class="order__id">
              <span>Order ID: #10040</span>
            </div>
            <div class="btn__back-to-shop">
              <button type="button" class="back">
                <img src="../assets/arrow-left.svg" alt="">
                Back to Shop
              </button>
            </div>
            <div class="personal__information">
              <div class="info">
                  <h5 class="info-headline">Name:</h5>
                  <span class="info-text">Oleo Bone</span>
                </div>     
                <div class="info">
                  <h5 class="info-headline">Email:</h5>
                  <span class="info-text">oleo_bone@gmail.com</span>
                </div>

                <div class="info">
                  <h5 class="info-headline">Shipping Address:</h5>
                  <span class="info-text">4140 Parker Rd. Allentown, New Mexico 31134</span>
                </div>
                <div class="info">
                  <h5 class="info-headline">Billing Address:</h5>
                  <span class="info-text">Same as shipping</span>
                </div>

                <div class="info">
                  <h5 class="info-headline">Shipping:</h5>
                  <span class="info-text">Free</span>
                </div>
                <div class="info">
                  <h5 class="info-headline">Payment Method:</h5>
                  <span class="info-text">Credit Card</span>
                </div>
            </div>
          </div>
        </div>
      <div class="col-12 col-md-6 cart-2" v-if="isDesktop">
        <div class="cart__wrapper">
          <OrderDetailsCollapseable/>
        </div>
      </div>
    </div>
  </div>

</template>
  
<script>
import { defineComponent } from 'vue';
import { useQuasar } from 'quasar';
import OrderDetailsCollapseable from 'src/components/OrderDetailsCollapseable.vue'
  
  export default defineComponent({
    name: "PageThanks",
    components: { 
      OrderDetailsCollapseable
    },
    computed: {
      isDesktop() {
        return this.$platform.is.desktop;
      },
      isTableOrMobile() {
        return this.$platform.is.tablet || this.$platform.is.mobile;
      }
    },
    created() {
      const $q = useQuasar()
      this.$platform = $q.platform;
    }

})
</script>

<style scoped>
  .thank-you-page__wrapper{
    margin: 0 auto;
  }
  .thanks-part{
    display: flex;
    align-items: flex-end;
    flex-direction: column;
    padding-right: 60px;
    padding-top: 60px;
  }
  .thanks-part-inner-wrapper{
    width: 540px;
    max-width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .thanks__for__order{
    display: flex;
    flex-direction: column;
    gap: 40px;
    align-items: center;
  }
  .thanks__for__order > img {
    width: 100px;
  }
  .thanks-text{
    display: flex;
    flex-direction: column;
    gap: 5px;
  }
  .thank-you-headling{
    font-weight: 600;
    font-size: 24px;
    line-height: 34px;
    text-align: center;
    color: #000034;
  }
  .thank-you-subheadling{
    font-weight: 500;
    font-size: 16px;
    line-height: 26px;
    text-align: center;
    color: #4B4E68;
  }
  .order__id{
    margin-top: 30px;
    background-color: rgba(228, 228, 255, 0.6);;
    border: 1px solid #7782F1;
    border-radius: 12px;
    padding: 6px 15px;
    font-weight: 500;
    font-size: 14px;
    line-height: 24px;
    text-align: center;
    color: #7782F1;
  }
  .btn__back-to-shop{
    margin-top: 30px;
  }
  .back{
    border-radius: 100px;
    background-color: #050824;
    padding: 16px 40px;
    font-weight: 600;
    font-size: 18px;
    line-height: 24px;
    color: #ffff;
    display: flex;
    gap: 6px;
    align-items: center;
    cursor: pointer;
  }
  .personal__information{
    background: #FFFFFF;
    border: 1px solid #D6D8EE;
    border-radius: 32px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 40px;
    padding-right: 71px;
    gap: 18px;
    width: 100%;
    margin-top: 50px;
  }
  .info-headline{
    font-weight: 400;
    font-size: 14px;
    line-height: 24px;
    color: #4B4E68;
  }
  .info-text{
    font-weight: 500;
    font-size: 14px;
    line-height: 24px;
  }
  .info{
    display: flex;
    flex-direction: column;
    gap: 2px;
  }
  .cart-2{
    background: rgba(239, 240, 245, 0.3);
    border-left: 1px solid #EBECF3;
    display: flex;
    align-items: flex-start;
    flex-direction: column;
    padding-left: 60px;
    padding-top: 60px;
  }
  .cart-2__wrapper{
    width: 450px;
    max-width: 100%;
    display: flex;
    flex-direction: column;
  }
.cart__contents-section::after{
  content: '';
  height: 1px;
  background: #D6D8EE;
  width: 100%;
}
</style>

<style scoped>
@media screen and (max-width: 576px) {
  .isMobile {
    width: 100%;
  }
  .show__order-mobile{
    width: 100%;
    padding: 16px;
    display: flex;
    align-items: center;
  }
  .show__order{
    display: flex;
    align-items: center;
    gap: 12px;
  }
  .thanks-part{
    padding: 30px 16px !important;
  }
  .cart__contents-section{
    display: flex;
    flex-direction: column;
    gap: 16px;
  }
  .thanks-part-inner-wrapper{
    margin-top: 30px;
  }
  .complete__order{
    margin-top: 30px;
    width: 100%;
    display: flex;
    justify-content: center;
  }
  .cart__wrapper{
    background-color: #ffff;
  }
  .cart__contents-section--wrapper{
    margin-top: 8px;
    padding: 20px 16px;
    background-color: var(--bg--cart);
    border-top: 1px solid #EBECF3;
    border-radius: 20px;
  }
  .jewellery__club-about{
    padding: 20px 16px;
  }
  .btn__back-to-shop{
    width: 100%;
  }
  .back{
    min-width: 100% !important;
    justify-content: center;
  }
  .personal__information{
    margin-top: 30px !important;
    display: flex !important;
    flex-direction: column;
    gap: 16px;
  }

}
 
</style>