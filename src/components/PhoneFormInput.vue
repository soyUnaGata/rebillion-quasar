<template>
    <div v-if="isTableOrMobile || showBox" class="form-input__wrapper w-100">
        <div class="phone__input">
          <PhoneCountryCodeSelect v-model="code"/>
          <input class="form-input--phone" type="text" name="phone" id="" v-model="phone">
        </div>
    </div> 
</template>


<script>
import { defineComponent } from 'vue';
import PhoneCountryCodeSelect from './PhoneCountryCodeSelect';
import { useQuasar } from 'quasar';

export default defineComponent({
  props:{
    modelValue: {
      type: String
    }
  },
  emits: ['update:modelValue'],
  name: 'PhoneFormInput',
  components: {
    PhoneCountryCodeSelect
  },
  data(){
    return {
      code: null,
      phone: '',
      showBox: false,
    }
  },
  watch: {
    code: function(value) {
      const phoneCode = value && value.phoneCode ? value.phoneCode : '';  
      this.$emit('update:modelValue', `${phoneCode}${this.phone}`)
    },
    phone: function(value){
      const phoneCode = this.code && this.code.phoneCode ? this.code.phoneCode : '';  
      this.$emit('update:modelValue', `${phoneCode}${value}`)
    }
  },
  computed:{
    isTableOrMobile(){
        return this.$platform.is.tablet || this.$platform.is.mobile;
      }
  },
  created(){
    const $q = useQuasar()
    this.$platform = $q.platform;
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