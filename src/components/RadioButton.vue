<template>
  <label :for="radioId" class="checkout-radio">
    <input type="radio" v-model="currentValue" :name="groupName" :id="radioId" style="display: none;" :value="value">
    <span class="checkout-radio-fake"></span>
    <span class="checkout-radio-text">{{ label }}</span>
  </label>  
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  props:{
    modelValue: {
      type: String,
      required: true
    },
    radioId: {
      type: String,
      required: true
    },
    groupName: {
      type: String,
      default: ''
    },
    value: {
      type: String,
      required: true
    },
    label: {
      type: String,
      default: ''
    }
  },
  emits: ['update:modelValue'],
  name: 'RadioButton',
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

<style scoped>
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
</style>