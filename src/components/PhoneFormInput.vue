<template>
    <div class="form-input__wrapper w-100 email__address__input">
        <div class="phone__input">
          <PhoneCountryCodeSelect />
          <input class="form-input--phone" type="text" name="phone" id="" v-model="currentValue">
        </div>
    </div> 
</template>


<script>
import { defineComponent } from 'vue'
import PhoneCountryCodeSelect from './PhoneCountryCodeSelect'

export default defineComponent({
  props:{
    modelValue: {
      type: String,
      required: true
    }
  },
  emits: ['update:modelValue'],
  name: 'PhoneFormInput',
  components: {
    PhoneCountryCodeSelect
  },
  computed:{
    currentValue: {
      get(){
        return this.modelValue;
      },
      set(val){
        this.$emit('update:modelValue', val)
      }
    }
  }
})
</script>

<style>
  .phone__input{
    display: flex;
    align-items: center;
    padding: 2px;
  }
  .form-input--phone{
    background-color: transparent;
    border: none;
    outline: none;
    font-size: 16px;
    width: 100%;
    color: var(--light--grey);
    font-weight: 500;
}
</style>