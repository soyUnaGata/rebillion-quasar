<template>
   <div class="checkout__wrapper">
    <div class="row h-100">
      <div class="col-12 col-md-8 shipping">
        <Shipping></Shipping>
      </div>
      <div class="col-12 col-md-4 cart">
        <div class="cart__wrapper">
          <Cart></Cart>
        </div>
      </div>
    </div>
   </div>
</template>

<style>
.checkout__wrapper{
  margin: 0 auto;
}
.h-100 {
    height: 100vh;
}
.row > .col-md-8 {
    width: 1005px;
    background-color: var(--bg--shipping);

} 
.row > .col-md-4 {
    width: 898px;
    background-color: var(--bg--cart);
}

.shipping{
  display: flex;
  align-items: flex-end;
  flex-direction: column;
  padding-right: 60px;
}
.cart{
  display: flex;
  align-items: flex-start;
  flex-direction: column;
  padding-left: 60px;
  padding-top: 60px;
}
.cart__wrapper{
  width: 450px;
  display: flex;
  flex-direction: column;
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