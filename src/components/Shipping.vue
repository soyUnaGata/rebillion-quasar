<template>
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

  <!-- <CountDown></CountDown> -->

  <div class="countdown">
    <p class="countdown-text"> 🔥 Your cart is reserved for 
      <span>10:00</span> 
      minutes
    </p>
    <div class="countdown-hms">
      <p class="hms hours">00</p>
      <p class="divide-dots">:</p>
      <p class="hms minutes">09</p>
      <p class="divide-dots">:</p>
      <p class="hms seconds">39</p>
    </div>
  </div>

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

  <form action="" method="get" class="regestration-form">
    <div class="regestration-form">
      <div class="regestration-form__rows shipping__address__select">
            <div class="form-input__wrapper w-100 country__select">
              <img class="select__arrow" src="../assets/select-country.svg" alt="" srcset="">
              <select class="form-input country__select-wrapper" name="Country" id="country">
                <option disabled="disabled" selected="selected" class="country-headline">Country</option>
                <option>Option 1</option>
              </select>
              <img class="form-input__img" src="../assets/location.svg" alt="">
            </div>
      </div>

      <div class="regestration-form__rows about__person">
        <div class="form-input__wrapper w-50-with-gap">
          <label class="form-input__label">First name</label>
          <img class="form-input__img" src="../assets/user.svg" alt="user-icon">
          <input class="form-input" type="text" name="name" id="name">
          
        </div>

        <div class="form-input__wrapper w-50-with-gap">
            <label class="form-input__label">Last name</label>
            <input class="form-input" type="text" name="last-name" id="last-name">
            <img class="form-input__img" src="../assets/user.svg" alt="user-icon">
        </div>

        <div class="form-input__wrapper w-100">
          <input class="form-input" type="text" name="adress" id="adress" placeholder="Address">
          <img class="form-input__img" src="../assets/home-location.svg" alt="home-location">
        </div>

        <div class="form-input__wrapper w-50-with-gap">
          <input class="form-input details" type="text" name="city" id="city" placeholder="City">
        </div>

        <div class="form-input__wrapper w-50-with-gap">
            <input class="form-input details" type="text" name="postal-code" id="postal-code" placeholder="Postal Code">
        </div>

      </div>
    </div>
  </form>

  <div class="shipping__method">
    <p class="shipping__method-text">Shipping method</p>
    <div class="check-shipping__method">
      <label for="free-shipping" class="free-shipping">
        <input type="radio" name="shipping" id="free-shipping" style="display: none;">
        <span class="free-shipping-radio-fake"></span>
        <span class="free-shipping-text">Free shipping</span>
      </label>

      <div class="dhl-shipping-price">
        <label class="dhl-shipping" for="dhl-shipping">
          <input type="radio" name="shipping" id="dhl-shipping" style="display: none;">
          <span class="dhl-shipping-radio-fake"></span>
          <span class="dhl-shipping-text">DHL with price</span>
        </label>

        <div class="shipping__cost">
          <span class="shipping__method-price">$0</span>
        </div>   
      </div>    
    </div>
   
  </div>

  <div class="payment__method">
    <p class="payment-text">Payment Method</p>
    <span>All transaction are secured and encryted</span>
  </div>

  <form action="" method="get" class="payment__form">
    <div class="payment__form card__holder-name">
      <div class="payment__form__rows">
        <div class="form-input__wrapper w-100">
          <label class="form-input__label" for="card">Card Number</label>
          <input class="form-input" type="text" name="card" id="card">
          <img  class="form-input__img" src="../assets/payment.svg" alt="card">
        </div>

        <div class="form-input__wrapper w-100">
          <input class="form-input" type="text" name="card-holder" id="card-holder" placeholder="Name on Card">
          <img class="form-input__img" src="../assets/user.svg" alt="user">
        </div>

        <div class="form-input__wrapper w-50-with-gap">
          <input class="form-input details" type="text" name="card-date" id="card-date" placeholder="MM/YY">
        </div>

        <div class="form-input__wrapper w-50-with-gap">
            <input class="form-input details" type="text" name="cvv" id="cvv" placeholder="CVV">
        </div>
      </div>

        <div class="user__agreements">
          <input type="checkbox" name="agreements" id="agreements" class="agreements">
          <label for="checkbox" class="user__agreements-text">By checking this box, I acknowledge that I have read and agree to the 
            <a href="" class="link-terms-policy">Terms of Service</a> and, 
            <a href="" class="link-terms-policy">Monthly Billing Terms </a> 
            of this website and want to opt-in for the monthly billed Dream Collection Club®
          </label>
        </div>
    </div>
  </form>

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

  <form action="" method="get" class="regestration-form other-shipping__address">
    <div class="regestration-form">
      <div class="regestration-form__rows shipping__address__select">
            <div class="form-input__wrapper w-100 country__select">
              <img class="select__arrow" src="../assets/select-country.svg" alt="" srcset="">
              <select class="form-input country__select-wrapper" name="Country" id="country">
                <option disabled="disabled" selected="selected" class="country-headline">Country</option>
                <option>Option 1</option>
              </select>
              <img class="form-input__img" src="../assets/location.svg" alt="">
            </div>
      </div>

      <div class="regestration-form__rows about__person">
        <div class="form-input__wrapper w-50-with-gap">
          <label class="form-input__label">First name</label>
          <img class="form-input__img" src="../assets/user.svg" alt="user-icon">
          <input class="form-input" type="text" name="name" id="name">
          
        </div>

        <div class="form-input__wrapper w-50-with-gap">
            <label class="form-input__label">Last name</label>
            <input class="form-input" type="text" name="last-name" id="last-name">
            <img class="form-input__img" src="../assets/user.svg" alt="user-icon">
        </div>

        <div class="form-input__wrapper w-100">
          <input class="form-input" type="text" name="adress" id="adress" placeholder="Address">
          <img class="form-input__img" src="../assets/home-location.svg" alt="home-location">
        </div>

        <div class="form-input__wrapper w-50-with-gap">
          <input class="form-input details" type="text" name="city" id="city" placeholder="City">
        </div>

        <div class="form-input__wrapper w-50-with-gap">
            <input class="form-input details" type="text" name="postal-code" id="postal-code" placeholder="Postal Code">
        </div>

      </div>

      <div class="submit__form-btn">
        <button class="complete__order" disabled="disabled" type="buttom">Complete Order<img class="img__arrow" src="../assets/Arrow-right.svg" alt="submit"></button>
      </div>
      

    </div>
  </form>

</template>

<style scoped>
.free-shipping-radio-fake, .dhl-shipping-radio-fake, .same-shipping-radio-fake, .other-shipping-radio-fake{
  border: 1px solid #000034;
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
.country__select-wrapper{
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  z-index: 22;
  position: absolute;
  cursor: pointer;
}
.select__arrow{
  top: 23px;
  position: absolute;
  right: 30px;
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
.countdown{
  margin-top: 50px;
  background-color: var(--bg--countdown);
  border-radius: 32px;
  width: 540px;
  height: 139px;
  color: var(--primary--dark);
}
.countdown-text{
  font-style: normal;
  padding-top: 30px;
  padding-left: 30px;
  font-weight: 500;
  font-size: 18px;
  line-height: 27px;
  color: var(--primary--dark);
}
.countdown-text > span {
  font-weight: 900;
}
.countdown-hms{
  margin-top: 15px;
  display: flex;
  gap: 8px;
  margin-left: 30px;
  align-items: center;
  width: 180px;
}
.hms{
  width: 46px;
  height: 37px;
  border-radius: 12px;
  background-color: var(--bg--shipping);
  align-items: center;
  display: flex;
  justify-content: center;
  font-weight: 500;
  font-size: 18px;
  line-height: 27px;
  color: var(--primary--dark);
}
.divide-dots{
  font-weight: 500;
}
.express__checkout{
  padding: 30px;
  width: 540px;
  height: 160px;
  border: 1px solid #D6D8EE;
  border-radius: 32px;
  margin-top: 30px;
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
.form-input__img {
    position: absolute;
    left: 39px;
    top: 18px;
}
.shipping__address{
  margin-top: 50px;
}
.shipping__address-text{
  font-weight: 600;
  font-size: 24px;
  line-height: 34px;
}
.about__person{
  margin-top: 30px;
}
.details{
  margin-left: 30px;
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
}
.free-shipping, .dhl-shipping{
  display: flex;
  gap: 10px;
  align-items: center;
  cursor: pointer;
}
.shipping__method-price{
  font-weight: 600;
  font-size: 36px;
  line-height: 46px;
  text-align: right;
  color: #000034;
}
.dhl-shipping-price{
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.shipping__cost{
  margin-right: 60px;
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
.card__holder-name{
  margin-top: 25px;
}
.user__agreements{
  display: flex;
  margin-top: 20px;
  width: 100%;
  line-height: 24px;
  gap: 12px;
}
input[type="checkbox"].agreements{
    content: '';
    min-width: 22px;
    height: 22px;
    -webkit-appearance: none;
    outline: none;
    background: #ECECEC;
}
input:checked[type="checkbox"].agreements{
    background-image: url(../assets/check.svg);
    background-position: center;
    background-repeat: no-repeat;
}
.user__agreements-text{
  font-weight: 400;
  font-size: 14px;
  line-height: 24px;
  margin-right: 60px;
  color: #4B4E68;
}
.link-terms-policy{
  text-decoration: none;
  color: #000034;
  font-weight: 600;
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
.shipping__address__select{
  padding-top: 20px;
}
.submit__form-btn{
  margin-top: 50px;
  position: relative;
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
}
.complete__order:disabled{
  background-color: rgba(5, 8, 36, 0.3);
}
</style>

<script>
import { defineComponent } from 'vue'
import CountDown from 'components/CountDown.vue'

export default defineComponent({
  name: ' Shipping',
  components: {
        CountDown,
      
    },
  
})
</script>
