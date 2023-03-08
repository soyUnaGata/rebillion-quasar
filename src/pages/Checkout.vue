<template>
    <div class="row h-100">
      <div class="col-12 col-md-8 shipping">
        <Shipping></Shipping>
      </div>
      <div class="col-12 col-md-4 cart">
        <Cart></Cart>
      </div>
    </div>
</template>

<style>
.h-100 {
    height: 100vh;
}
.row > .col-md-8 {
    width: 1005px;
    background-color: var(--bg--shipping);
    padding-left: 405px;
    padding-bottom: 350px;
} 
.row > .col-md-4 {
    width: 898px;
    background-color: var(--bg--cart);
    padding-top: 60px;
    padding-left: 61px;
    padding-right: 405px;
}
</style>
  
<script>
  import { defineComponent } from 'vue';
  import Shipping from 'components/Shipping.vue';
  import Cart from 'components/Cart.vue';
  
  export default defineComponent({
    name: 'PageCheckout',

    components: {
        Shipping,
        Cart,
    },
  })
</script> 