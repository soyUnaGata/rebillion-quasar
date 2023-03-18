<template>
   <div class="checkout__wrapper">
    <div class="row h-100">
      <div class="shipping col-12 col-md-6">
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
            <div class="isMobile" >
              <OrderDetailsCollapseable v-if="isTableOrMobile" />
            </div>
          <CountDown />
          <ExpressCheckout />
          <div class="contanct__info">
            <h3 class="contact__info-text">Contact Information</h3>

            <div class="form-input__wrapper w-100 email__address__input" :class="{ 'form-control--invalid': v$?.checkout.email.$invalid }"> 
              <div class="email__input">
                <label class="form-input__label email-text">Email Address</label>
                <img class="form-input__img" src="../assets/mail-icon.svg" alt="">
                <input class="form-input" type="email" name="email" v-model="checkout.email">
              </div>
              <span class="form-error-message">Enter a email address</span> 
            </div>
            <PhoneFormInput v-model="checkout.phone"/>
          </div>
          <div class="shipping__address">
            <h3 class="shipping__address-text">Shipping Address</h3>
          </div>
          <AddressForm v-model="checkout.shippingAddress" :countries="countries"/>
          <div class="shipping__method">
            <h3 class="shipping__method-text">Shipping method</h3>
            <div class="check-shipping__method">
              <div class="dhl-shipping-price">
                <RadioButton v-model="checkout.shippingMethod" radio-id="free-shipping" group-name="shipping-method" value="1" label="Free shipping"/>
                <RadioButton v-model="checkout.shippingMethod" radio-id="dhl-shipping" group-name="shipping-method" value="2" label="DHL with price"/>
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
          <CardPaymentMethodForm v-model="checkout.paymentMethod" />
          <div class="billing__address">
            <h3 class="billing-text">Billing Address</h3>
            <span>Specify the address for your payment option</span>

            <div class="check-billing__address">   
              <RadioButton v-model="checkout.billingAddressType" radio-id="same-shipping" group-name="billing-address" value="1" label="Same as shipping address"/>
              <RadioButton v-model="checkout.billingAddressType" radio-id="diff-shipping" group-name="billing-address" value="2" label="Use a different billing address"/>
            </div>
          </div>
          <AddressForm v-if="checkout.billingAddressType == 2" v-model="checkout.billingAddress" :countries="countries" />
          <button class="complete__order" :disabled="isInvalid" type="button" @click="submit">Complete Order
            <img class="img__arrow" src="../assets/Arrow-right.svg" alt="submit">
          </button>
          <SafePaymentSSL v-if="isTableOrMobile"/>
        </div>
      </div>
      <div class="col-12 col-md-6 cart">
        <div class="cart__wrapper">
          <OrderDetailsCollapseable v-if="isDesktop"/>
        </div>
      </div>
    </div>
   </div>
</template>
  
<script>
  import { defineComponent } from 'vue';
  import { useQuasar } from 'quasar';
  import { useVuelidate } from '@vuelidate/core' 
  import { required, requiredIf, email, numeric, minLength, maxLength } from '@vuelidate/validators' 
 
  import Constants from '../common/Constants'
  import CountDown from 'src/components/CountDown.vue';
  import AddressForm from 'src/components/AddressForm.vue';
  import CardPaymentMethodForm from 'src/components/CardPaymentMethodForm.vue';
  import ExpressCheckout from 'src/components/ExpressCheckout.vue';
  import OrderDetails from 'src/components/OrderDetails.vue';
  import SafePaymentSSL from 'src/components/SafePaymentSSL.vue';
  import JewelleryClub from 'src/components/JewelleryClub.vue'
  import RadioButton from 'src/components/RadioButton.vue'
  import OrderDetailsCollapseable from 'src/components/OrderDetailsCollapseable.vue'
  import PhoneFormInput from 'src/components/PhoneFormInput.vue';

  const requiredIfBillingAddressTypeIsNotSame = (value, siblings, vm) => {
    const invalidValue = !value || value === ' ';
    return vm.checkout.billingAddressType == 1 || !invalidValue;
  }

  export default defineComponent({
    name: 'PageCheckout',
    components: {
        CountDown,
        ExpressCheckout,
        AddressForm,
        CardPaymentMethodForm,
        OrderDetails,
        SafePaymentSSL,
        JewelleryClub,
        RadioButton,
        OrderDetailsCollapseable,
        PhoneFormInput
    },
    setup: () => ({ v$: useVuelidate() }), 
    data() {
        return {
            mobile: false,
            showOrder: false,
            showCart: true,
            checkout: {
                email: '',
                phoneNumber: '',
                shippingAddress: {
                    countryId: null,
                    firstName: '',
                    lastName: '',
                    address: '',
                    city: '',
                    postalCode: ''
                },
                shippingMethod: 1,
                paymentMethod: {
                    cardNumber: '',
                    cardHolder: '',
                    expired: '',
                    cvv: '',
                    agree: false
                },
                billingAddressType: 1,
                billingAddress: {
                    countryId: null,
                    firstName: '',
                    lastName: '',
                    city: '',
                    postalCode: ''
                }
            }
        }
    },
    validations: { 
        checkout: {
            email: {
                required,
                email,
            },
            shippingAddress: {
              firstName: { required },
              lastName: { required }
            },
            paymentMethod: {
              cardNumber: {
                required,
                numeric,
                maxLength: maxLength(16),
                minLength: minLength(16)
              }
            },
            billingAddress: {
              firstName: { requiredIfBillingAddressTypeIsNotSame },
              lastName: { requiredIfBillingAddressTypeIsNotSame }
            }
        }
    },
    computed: {
        isDesktop() {
            return this.$platform.is.desktop;
        },
        isTableOrMobile() {
            return this.$platform.is.tablet || this.$platform.is.mobile;
        },
        countries() {
            return Constants.countries.map((c, i) => ({
                id: i,
                name: c
            }));
        },
        isInvalid(){
          return this.v$.checkout.$invalid;
        }
    },
    methods:{
      submit(){
        if(this.isInvalid) return;

        //send request, if success then:
        this.$router.push('/upsell');
      }
    },
    created() {
        const $q = useQuasar()
        this.$platform = $q.platform;
    }
  })

</script> 

<style>
.checkout__wrapper{
  margin: 0 auto;
}
.h-100 {
    height: 100vh;
}
.order-wrapper {
  max-height: 0;
  overflow: hidden;
  transition:  0.5s ease-in-out;
}

.order-wrapper:focus {
  max-height: 500px;
}
.show__order{
  padding: 25px;
  display: flex;
  gap: 15px;
  align-items: center;
}
.summary{
  padding: 24px;
  align-items: center;
  display: flex;
}
.cart__contents-section{
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 16px;
}
.shipping{
  display: flex;
  align-items: flex-end;
  flex-direction: column;
  padding-right: 60px;
  background-color: var(--bg--shipping);
}
.cart{
  display: flex;
  align-items: flex-start;
  flex-direction: column;
  padding-left: 60px;
  padding-top: 60px;
  background-color: var(--bg--cart);
}
.shipping__wrapper{
  width: 540px;
  max-width: 100%;
  display: flex;
  flex-direction: column;
}
.checkout-radio-fake {
  border: 1px solid #D6D8EE;
  height: 24px;
  width: 24px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}
.checkout-radio input[type="radio"]:checked + .checkout-radio-fake::after{
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
  padding-top: 20px;
}
.checkout-radio {
  display: flex;
  gap: 10px;
  font-weight: 500;
  font-size: 16px;
  line-height: 24px;
  color: #4B4E68;
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
  display: flex;
  flex-direction: column;
  gap: 5px;
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
  max-width: 100%;
}
.complete__order:disabled{
  background-color: rgba(5, 8, 36, 0.3);
}
</style>

<style>
  @media screen and (max-width: 576px) {
    .shipping{
      padding: 30px 16px;
      max-width: 100%;
      gap: 30px;
      display: flex;
    }
    .isMobile {
      margin-top: 30px;
    }
    .cart{
      padding: 0px;
      background-color: var(--bg--shipping);
    }
    .w-50-with-gap{
      width: 100%;
    }
    .breadcrumbs__h1{
      margin-top: 30px;
    }
    .countdown{
      padding: 16px;
      max-width: 100%;
      align-items: center;
      display: flex;
      flex-direction: column;
    }
    .countdown-text{
      text-align: center;
    }
    .countdown-hms{
      padding: 16px;
      margin: 0;
    }
    .express__checkout{
      max-height: 100%;
    }
    .payment_type{
      flex-wrap: wrap;
    }
    .email__address__input {
      margin-top: 20px;
    }
    .form-input--phone{
      padding-left: 10px;
    }
    .shipping__address {
      margin-top: 30px;
    }
    .about__person{
      margin-top: 20px;
    }
    .shipping__method{
      margin-top: 20px;
    }
    .payment__method{
      margin-top: 30px;
    }
    .billing__address{
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
    .safe__payment-about{
      margin-top: 30px !important;
    }

  }
</style>