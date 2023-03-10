<template>

  <OrderDetails/>

  <SafePaymentSSL/>

 <JewelleryClub/>

</template>
<style scoped>




</style>

<script>
import { defineComponent } from 'vue'
import OrderDetails from './OrderDetails.vue';
import SafePaymentSSL from './SafePaymentSSL.vue';
import JewelleryClub from './JewelleryClub.vue'

export default defineComponent({
    name: "Cart",
    components: { OrderDetails, SafePaymentSSL, JewelleryClub }
})
</script>
