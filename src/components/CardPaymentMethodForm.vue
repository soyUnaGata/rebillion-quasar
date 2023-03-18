<template>
        <div class="payment__form card__holder-name">
      <div class="payment__form__rows">
        <div class="form-input__wrapper w-100" :class="{ 'form-control--invalid': v$?.modelValue.cardNumber.$invalid }">
          <label class="form-input__label" for="card">Card Number</label>
          <input class="form-input" type="text" name="card" id="card" v-model="modelValue.cardNumber">
          <img  class="form-input__img" src="../assets/payment.svg" alt="card">
          <span class="form-error-message">Enter valid card number </span>
        </div>

        <div class="form-input__wrapper w-100">
          <input class="form-input" type="text" name="card-holder" id="card-holder" placeholder="Name on Card" v-model="modelValue.cardHolder">
          <img class="form-input__img" src="../assets/user.svg" alt="user">
        </div>

        <div class="form-input__wrapper w-50-with-gap">
          <input class="form-input details" type="text" name="card-date" id="card-date" placeholder="MM/YY" v-model="modelValue.expired">
        </div>

        <div class="form-input__wrapper w-50-with-gap">
            <input class="form-input details" type="password" name="cvv" id="cvv" placeholder="CVV" v-model="modelValue.cvv">
        </div>
      </div>

        <div class="user__agreements">
          <input type="checkbox" name="agreements" id="agreements" class="agreements" v-model="modelValue.agree">
          <label for="checkbox" class="user__agreements-text">By checking this box, I acknowledge that I have read and agree to the 
            <a href="" class="link-terms-policy">Terms of Service</a> and, 
            <a href="" class="link-terms-policy">Monthly Billing Terms </a> 
            of this website and want to opt-in for the monthly billed Dream Collection Club®
          </label>
        </div>
    </div>
</template>

<script>
import { defineComponent } from 'vue'
import { useVuelidate } from '@vuelidate/core' 
import { required, numeric, minLength, maxLength } from '@vuelidate/validators' 

export default defineComponent({
  name: 'CardPaymentMethodForm',
  props: {
    modelValue: {
      type: Object,
      default: {
          cardNumber: null,
          cardHolder: '',
          expired: '',
          cvv: '',
          agree: false
        }
      }
  },
  setup: () => ({ v$: useVuelidate() }), 
  validations:{
    modelValue:{
      cardNumber: {
        required,
        numeric,
        maxLength: maxLength(16),
        minLength: minLength(16)
      }
    }
  }
})
</script>

<style scoped>
.card__holder-name{
  margin-top: 30px;
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
  color: #4B4E68;
}
.link-terms-policy{
  text-decoration: none;
  color: #000034;
  font-weight: 600;
}
</style>