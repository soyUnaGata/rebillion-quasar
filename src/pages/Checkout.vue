<template>
   <div class="checkout__wrapper">
    <div class="row h-100">
      <div class="col-12 col-md-8 shipping">
        <div class="shipping__wrapper">
          <div class="breadcrumbs__h1">
          <div class="path__cart">
            <h2>Checkout</h2>
          </div>
          <q-breadcrumbs>
            <template v-slot:separator>
              <q-icon
                size="8px"
                name="chevron_right"
                color= "#000034"
              />
            </template>
            <q-breadcrumbs-el label="Cart" class="breadcrumbs__cart-link"/>
            <q-breadcrumbs-el label="Shipping & Billing" class="breadcrumbs__cart"/>
          </q-breadcrumbs>
          </div>
          <CountDown />
          <ExpressCheckout />
          <div class="contanct__info">
            <h3 class="contact__info-text">Contact Information</h3>

            <div class="form-input__wrapper w-100 email__address__input">
              <div class="email__input">
                <label class="form-input__label email-text">Email Address</label>
                <img class="form-input__img" src="../assets/mail-icon.svg" alt="">
                <input class="form-input" type="email" name="email" id="">
              </div>
            </div>
          </div>
          <div class="shipping__address">
            <h3 class="shipping__address-text">Shipping Address</h3>
          </div>
          <AddressForm />
          <div class="shipping__method">
            <h3 class="shipping__method-text">Shipping method</h3>
            <div class="check-shipping__method">
              <div class="dhl-shipping-price">
                <label for="free-shipping" class="free-shipping">
                  <input type="radio" name="shipping" id="free-shipping" style="display: none;">
                  <span class="free-shipping-radio-fake"></span>
                  <span class="free-shipping-text">Free shipping</span>
                </label>
                <label class="dhl-shipping" for="dhl-shipping">
                    <input type="radio" name="shipping" id="dhl-shipping" style="display: none;">
                    <span class="dhl-shipping-radio-fake"></span>
                    <span class="dhl-shipping-text">DHL with price</span>
                </label>
              </div>    
              <div class="shipping__cost">
                  <span class="shipping__method-price">$0</span>
              </div> 
            </div>
          
          </div>
          <div class="payment__method">
            <h3 class="payment-text">Payment Method</h3>
            <span>All transaction are secured and encryted</span>
          </div>
          <CardPaymentMethodForm />
          <div class="billing__address">
            <h3 class="billing-text">Billing Address</h3>
            <span>Specify the address for your payment option</span>

            <div class="check-billing__address">   
              <label for="same-shipping" class="same-shipping">
                <input type="radio" name="billing" id="same-shipping" style="display: none;">
                <span class="same-shipping-radio-fake"></span>
                <span class="same-shipping-text">Same as shipping address</span>
              </label>  
              <label for="other-shipping" class="other-shipping">
                <input type="radio" name="billing" id="other-shipping" style="display: none;">
                <span class="other-shipping-radio-fake"></span>
                <span class="other-shipping-text">Use a different billing address</span>
              </label>
            </div>
          </div>
          <AddressForm />
          <button class="complete__order" disabled="disabled" type="buttom">Complete Order
            <img class="img__arrow" src="../assets/Arrow-right.svg" alt="submit">
          </button>
        </div>
      </div>
      <div class="col-12 col-md-4 cart">
        <div class="cart__wrapper">
          <Cart></Cart>
        </div>
      </div>
    </div>
   </div>
</template>

<style>
.checkout__wrapper{
  margin: 0 auto;
}
.h-100 {
    height: 100vh;
}
.row > .col-md-8 {
    width: 1005px;
    background-color: var(--bg--shipping);

} 
.row > .col-md-4 {
    width: 898px;
    background-color: var(--bg--cart);
}

.shipping{
  display: flex;
  align-items: flex-end;
  flex-direction: column;
  padding-right: 60px;
}
.cart{
  display: flex;
  align-items: flex-start;
  flex-direction: column;
  padding-left: 60px;
  padding-top: 60px;
}
.cart__wrapper{
  width: 450px;
  display: flex;
  flex-direction: column;
}
</style>
  
<script>
  import { defineComponent } from 'vue';
  import Shipping from 'components/Shipping.vue';
  import Cart from 'components/Cart.vue';
  
  export default defineComponent({
    name: 'PageCheckout',

    components: {
        Shipping,
        Cart,
    },
  })
</script> 