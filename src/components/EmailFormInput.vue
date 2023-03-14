<template>
    <div class="form-input__wrapper w-100 email__address__input">
        <div class="email__input">
        <label class="form-input__label email-text">Email Address</label>
        <img class="form-input__img" src="../assets/mail-icon.svg" alt="">
            <input class="form-input" type="email" name="email" id="" v-model="currentValue">
        </div>
    </div> 
</template>


<script>
import { defineComponent } from 'vue'

export default defineComponent({
  props:{
    modelValue: {
      type: String,
      required: true
    }
  },
  emits: ['update:modelValue'],
  name: 'EmailFormInput',
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