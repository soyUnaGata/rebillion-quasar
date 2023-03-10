<template>
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
      <p class="contact__info-text">Contact Information</p>

      <div class="form-input__wrapper w-100 email__address__input">
        <div class="email__input">
          <label class="form-input__label email-text">Email Address</label>
          <img class="form-input__img" src="../assets/mail-icon.svg" alt="">
          <input class="form-input" type="email" name="email" id="">
        </div>
      </div>
    </div>

    
    <div class="shipping__address">
      <p class="shipping__address-text">Shipping Address</p>
    </div>

    <AddressForm />

    <div class="shipping__method">
      <p class="shipping__method-text">Shipping method</p>
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
      <p class="payment-text">Payment Method</p>
      <span>All transaction are secured and encryted</span>
    </div>

    <CardPaymentMethodForm />

    <div class="billing__address">
      <p class="billing-text">Billing Address</p>
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

    <button class="complete__order" disabled="disabled" type="buttom">Complete Order<img class="img__arrow" src="../assets/Arrow-right.svg" alt="submit"></button>
</div>

</template>

<style scoped>
.shipping__wrapper{
  width: 540px;
  display: flex;
  flex-direction: column;
}
.free-shipping-radio-fake, .dhl-shipping-radio-fake, .same-shipping-radio-fake, .other-shipping-radio-fake{
  border: 1px solid #D6D8EE;
  height: 24px;
  width: 24px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}
.free-shipping input[type="radio"]:checked + .free-shipping-radio-fake::after{
  content: '';
  display: flex;
  height: 12px;
  width: 12px; 
  background-color: #4B4E68;
  border-radius: 50%;
}
.dhl-shipping input[type="radio"]:checked + .dhl-shipping-radio-fake::after{
  content: '';
  display: flex;
  height: 12px;
  width: 12px; 
  background-color: #4B4E68;
  border-radius: 50%;
}
.same-shipping input[type="radio"]:checked + .same-shipping-radio-fake::after{
  content: '';
  display: flex;
  height: 12px;
  width: 12px; 
  background-color: #4B4E68;
  border-radius: 50%;
}
.other-shipping input[type="radio"]:checked + .other-shipping-radio-fake::after{
  content: '';
  display: flex;
  height: 12px;
  width: 12px; 
  background-color: #4B4E68;
  border-radius: 50%;
}


.breadcrumbs__h1{
  margin-top: 60px;
}

h2{
  font-style: normal;
  font-weight: 700;
  font-size: 36px;
  line-height: 46px;
  text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  color: var(--primary--dark);
}
.breadcrumbs__cart{
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 24px;
  text-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  color: var(--primary--dark) !important;
}
.breadcrumbs__cart-link{
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 24px;
  text-decoration: none;
  color:var(--light--grey) !important;
}


.contanct__info{
  margin-top: 50px;
}
.contact__info-text{
  font-weight: 600;
  font-size: 24px;
  line-height: 34px;
  color: var(--primary--dark);
}
.email__address__input{
  margin-top: 29px;
}

.shipping__address{
  margin-top: 50px;
}
.shipping__address-text{
  font-weight: 600;
  font-size: 24px;
  line-height: 34px;
}


.shipping__method{
  margin-top: 50px;
  color: #000034;
}
.shipping__method-text{
  font-weight: 500;
  font-size: 24px;
  line-height: 34px;
  color: #000034;
}
.check-shipping__method{
  font-weight: 500;
  font-size: 16px;
  line-height: 24px;
  color: #4B4E68;
  display: flex;
}
.free-shipping, .dhl-shipping{
  display: flex;
  gap: 10px;
  align-items: center;
  cursor: pointer;
}
.shipping__method-price{

  display: flex;
}
.dhl-shipping-price{
  display: flex;
  flex-direction: column;
  width: 100%;
  gap: 20px;
}
.shipping__cost{
  font-weight: 600;
  font-size: 36px;
  text-align: right;
  color: #000034;
  display: flex;
  align-items: flex-end;
  justify-content: flex-end;
  width: 50px;
}
.payment__method{
  margin-top: 50px;
}
.payment-text{
  font-weight: 600;
  font-size: 24px;
  line-height: 34px;
  color: #000034;
}
.payment__method > span{
  font-weight: 400;
  font-size: 14px;
  line-height: 21px;
  color: #84849A;
}

.billing__address{
  margin-top: 50px;
}
.billing-text{
  font-weight: 600;
  font-size: 24px;
  line-height: 34px;
}
.billing__address > span{
  font-weight: 400;
  font-size: 14px;
  line-height: 21px;
  color: #84849A;
}
.check-billing__address{
  display: flex;
  flex-direction: column;
  gap: 20px;
  margin-top: 20px;
}
.same-shipping,.other-shipping{
  display: flex;
  gap: 10px;
  font-weight: 500;
  font-size: 16px;
  line-height: 24px;
  color: #4B4E68;
  cursor: pointer;
}
.complete__order{
  display: flex;
  padding: 16px 40px;
  gap: 6px;
  height: 56px;
  background: #050824;
  border-radius: 100px;
  color: var(--bg--shipping);
  font-weight: 600;
  font-size: 18px;
  line-height: 24px;
  cursor: pointer;
  border: none;
  align-items: center;
  margin-top: 50px;
  width: 257px;
}
.complete__order:disabled{
  background-color: rgba(5, 8, 36, 0.3);
}
</style>

<script>
import { defineComponent } from 'vue'
import CountDown from './CountDown.vue'
import AddressForm from './AddressForm.vue'
import CardPaymentMethodForm from './CardPaymentMethodForm'
import ExpressCheckout from './ExpressCheckout'

export default defineComponent({
  name: ' Shipping',
  components: {
      CountDown,
      AddressForm,
      CardPaymentMethodForm,
      ExpressCheckout
    },
  
})
</script>
