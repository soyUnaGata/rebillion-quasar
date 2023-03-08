<template>
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
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'AddressForm'
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