<template>
  <div class="thank-you-page__wrapper">
    <div class="row">
      <div class="col-12 col-md-6 thanks-part">  
        <div class="thanks__for__order">
          <img src="../assets/like.png" alt="">
          <div class="thanks-text">
            <h2 class="thank-you-headling">Thank you for your order</h2>
            <h4 class="thank-you-subheadling">Your order is confirmed</h4>
          </div>
        </div>
        <div class="order__id">
          <span>Order ID: #10040</span>
        </div>
      </div>
      <div class="col-12 col-md-6 cart">
      </div>
    </div>

  </div>

</template>
  
<script>
  import { defineComponent } from 'vue';
  
  export default defineComponent({
    name: 'PageThanks'
  })
</script>

<style scoped>
  .thank-you-page__wrapper{
    padding-top: 60px;
    margin: 0 auto;
  }
  .thanks-part{
    display: flex;
    align-items: center;
    flex-direction: column;
  }
  .thanks__for__order{
    display: flex;
    flex-direction: column;
    gap: 40px;
    align-items: center;
  }
  .thanks__for__order > img {
    width: 100px;
  }
  .thanks-text{
    display: flex;
    flex-direction: column;
    gap: 5px;
  }
  .thank-you-headling{
    font-weight: 600;
    font-size: 24px;
    line-height: 34px;
    text-align: center;
    color: #000034;
  }
  .thank-you-subheadling{
    font-weight: 500;
    font-size: 16px;
    line-height: 26px;
    text-align: center;
    color: #4B4E68;
  }
  .order__id{
    margin-top: 30px;
    background-color: rgba(228, 228, 255, 0.6);;
    border: 1px solid #7782F1;
    border-radius: 12px;
    padding: 6px 15px;
    font-weight: 500;
    font-size: 14px;
    line-height: 24px;
    text-align: center;
    color: #7782F1;
  }
</style>
