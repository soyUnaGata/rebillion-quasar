<template>
    <div class="regestration-form">
      <div class="regestration-form__rows shipping__address__select">
            <div class="form-input__wrapper w-100 country__select">
              <img class="select__arrow" src="../assets/select-country.svg" alt="" srcset="">
              <select class="form-input country__select-wrapper" name="Country" id="country" v-model="modelValue.countryId">
                <option disabled="disabled" selected="selected" class="country-headline">Country</option>
                <option v-for="country in countries" :value="country.id" v-text="country.name"></option>
              </select>
              <img class="form-input__img" src="../assets/location.svg" alt="">
            </div>
      </div>

      <div class="regestration-form__rows about__person">
        <div class="form-input__wrapper w-50-with-gap" :class="{ 'form-control--invalid': v$?.modelValue.firstName.$invalid }">
          <label class="form-input__label">First name</label>
          <img class="form-input__img" src="../assets/user.svg" alt="user-icon">
          <input class="form-input" type="text" name="name" id="name" v-model="modelValue.firstName">
          <span class="form-error-message">Enter a first name</span>
        </div>

        <div class="form-input__wrapper w-50-with-gap" :class="{ 'form-control--invalid': v$?.modelValue.lastName.$invalid }">
            <label class="form-input__label">Last name</label>
            <input class="form-input" type="text" name="last-name" id="last-name" v-model="modelValue.lastName">
            <img class="form-input__img" src="../assets/user.svg" alt="user-icon">
            <span class="form-error-message">Enter a last name</span>
        </div>

        <div class="form-input__wrapper w-100">
          <input class="form-input" type="text" name="adress" id="adress" placeholder="Address" v-model="modelValue.address" >
          <img class="form-input__img" src="../assets/home-location.svg" alt="home-location">
        </div>

        <div class="form-input__wrapper w-50-with-gap">
          <input class="form-input details" type="text" name="city" id="city" placeholder="City" v-model="modelValue.city">
        </div>

        <div class="form-input__wrapper w-50-with-gap">
            <input class="form-input details" type="text" name="postal-code" id="postal-code" placeholder="Postal Code" v-model="modelValue.postalCode">
        </div>

      </div>     

    </div>
</template>

<script>
import { defineComponent } from 'vue'
import { useVuelidate } from '@vuelidate/core'
import { required } from '@vuelidate/validators'

export default defineComponent({
  name: 'AddressForm',
  props: {
    modelValue: {
      type: Object,
      default: {
        countryId: null,
        firstName: '',
        lastName: '',
        address: '',
        city: '',
        postalCode: ''
      } 
    },
    countries: {
      type: Array
    }
  },
  setup: () => ({ v$: useVuelidate() }),
  validations:{
    modelValue: {
      firstName: { required },
      lastName: { required }
    }
  }
})
</script>


<style scoped>
.about__person{
  margin-top: 30px;
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
.shipping__address__select{
  padding-top: 20px;
}


</style>