<template>
  <div class="page__wrapper">
    <div class="cart-item-slider">
      <img class="cart-item-img__middle" src="../assets/sneakers_pink-bg-mid.png" alt="">
      <div class="slider-navigation">
        <button class="btn-left" type="button"></button>
        <button class="btn-right" type="button"></button>
        
      </div>     
    </div>
    <div class="quantity-item__wrapper">
      <div class="price__and__discount">
        <span class="title-price">Price:
          <span class="value-price">$50</span>
        </span>
        <span class="discount">-80%</span>
      </div>
      <div class="quantity-item__count">
        <span class="quantity-text">
          Quantity:
          <div class="d-increase-quantity__btns">
            <button class="decrease same-style" type="button">-</button>
            <span>1</span>
            <button class="increase same-style" type="button">+</button>
          </div>
        </span>
      </div>
    </div>
    <div class="description__section">
      <span class="title__description">Ornare rhoncus nunc ut felis. Faucibus dolor at ultrices tincidunt. Pulvinar sed justo et viverra pellentesque.</span>
      <br>
      <br>
      <span class="description">Mauris augue nulla proin vel a. Facilisis fringilla molestie dignissim elit orci malesuada. Lorem sit sagittis vitae nulla id. Mauris ipsum sed sed faucibus. Nulla amet metus gravida orci faucibus nisl eros arcu lorem. Nullam ornare molestie nam id gravida volutpat bibendum sem feugiat. Neque vulputate in et maecenas porta mi tellus. In massa porttitor urna quis volutpat at.</span>
    </div>
    <div class="support__security__section">
      <div class="secure__section">
        <div class="secure__section-about">
          <img src="../assets/secure-img.svg" alt="" class="secure-img">
          <span class="secure-headline">
          Guaranteed 
          <a href="#" class="safe">Safe</a> & 
          <a href="#" class="safe">Secure</a> Checkout
          </span>
        </div>
    
        <div class="payment__group-section">
          <img src="../assets/secure-section-img-1.png" alt="">
          <img src="../assets/secure-section-img-2.png" alt="">
          <img src="../assets/secure-section-img-3.png" alt="">
          <img src="../assets/secure-section-img-4.png" alt="">
          <img src="../assets/secure-section-img-5.png" alt="">
          <img src="../assets/secure-section-img-6.png" alt="">
        </div>
      </div>
      <div class="support__section" v-if="isDesktop">
        <div class="support-about">
          <img src="../assets/support-person.svg" alt="">
          <div class="support-text">
            <span class="work-hours">24/7</span>
            <span class="support-headline">Support</span>
          </div>
        </div>
      </div>
    </div>
    <div class="submit__purchase-btn">
      <div class="submit__purchase">
        <button class="purchase" type="button" @click="submit">
          Yes, I want
          <img src="../assets/Arrow-right.svg" alt="">
        </button>
      </div>
      <div class="reject__purchase">
        <router-link :to="'/thank-you'"><span>No, Thanks</span></router-link>
      </div>
    </div>
  </div>
</template>
  
<script>
  import { defineComponent } from 'vue';
  import { useQuasar } from 'quasar';

  export default defineComponent({
    name: 'PageUpsell',
    computed: {
        isDesktop() {
            return this.$platform.is.desktop;
        },
        isTableOrMobile() {
            return this.$platform.is.tablet || this.$platform.is.mobile;
        },
      },
      created() {
        const $q = useQuasar()
        this.$platform = $q.platform;
      },
      methods:{
      submit(){
        this.$router.push('/thank-you');
      }
    },
  })
</script>

<style scoped>
  .page__wrapper{
    padding: 60px 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    /* max-width: 790px; */
    margin: 0 auto;
    max-width: 100%;
  }
  .cart-item-slider{
    position: relative;
  }
  .slider-navigation{
    display: flex;
    width: 100%;
    height: 40px;
    position: absolute;
    padding: 0 30px;
    top: 50%;
    transform: translate(0,-50%);
    justify-content: space-between;
  }
  .btn-left{
    border: none;
    background: url(../assets/btn-left.svg);
    width: 40px;
    background-repeat: no-repeat;
    background-size: contain;
    cursor: pointer;
  }
  .btn-right{
    border: none;
    background: url(../assets/right-arrow-slider.svg);
    width: 40px;
    background-repeat: no-repeat;
    background-size: contain;
    cursor: pointer;
  }
  .quantity-item__wrapper{
    margin-top: 30px;
    background: #FFFFFF;
    border: 1px solid #DADDF5;
    box-shadow: 0px 10px 30px rgba(22, 8, 49, 0.05);
    border-radius: 16px;
    width: 790px;
    max-width: 100%;
    padding: 40px 125px;
  }
  .price__and__discount{
    padding-top: 40px;
    display: flex;
    gap: 12px;
    justify-content: center;
    align-items: center;
  }
  .title-price{
    display: flex;
    gap: 10px;
    font-weight: 500;
    font-size: 20px;
    line-height: 30px;
    color: var(--primary--dark);
    align-items: center;
  }
  .value-price{
    font-weight: 600;
    font-size: 30px;
    line-height: 40px;
  }
  .discount{
    padding: 3px 15px;
    background: #EFF0F5;
    border-radius: 8px;
    font-weight: 500;
    font-size: 20px;
    line-height: 30px;
  }
  .quantity-item__count{
    margin-top: 25px;
    background-color:rgba(239, 240, 245, 0.5);
    border-radius: 16px;
    height: 80px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .quantity-text{
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 39px;
  }
  .d-increase-quantity__btns{
    display: flex;
    gap: 30px;
    align-items: center;
  }
  .same-style{
    background-color: #FFFFFF;
    border-radius: 16px;
    padding: 15px 19px;
    cursor: pointer;
    font-size: 25px;
    border: none;
    line-height: 20px;
    font-weight: 400;
    color: var(--primary--dark);
  }
  .d-increase-quantity__btns > span{
    font-weight: 600;
    font-size: 20px;
    line-height: 30px;
    color: var(--primary--dark);
  }
  .quantity-text{
    font-weight: 500;
    font-size: 20px;
    line-height: 30px;
    color: #4B4E68;
  }
  .description__section{
    margin-top: 40px;
    width: 790px;
  }
  .title__description{
    font-weight: 500;
    font-size: 18px;
    line-height: 28px;
    color: #4B4E68;
  }
  .description{
    font-weight: 400;
    font-size: 18px;
    line-height: 28px;
    color: #4B4E68;
  }
  .support__security__section{
    display: flex;
    gap: 30px;
    margin-top: 40px;
  }
  .secure__section{
    background: #FFFFFF;
    border: 1px solid #DADDF5;
    box-shadow: 0px 10px 30px rgba(22, 8, 49, 0.05);
    border-radius: 16px;
    display: flex;
    flex-direction: column;
    padding: 30px 70px;
  }
.secure__section-about{
  display: flex;
  gap: 15px;
  align-items: center;
}
  .payment__group-section{
    padding-top: 30px;
    display: flex;
    gap: 15px;
  }
  .safe{
    font-weight: 600;
    font-size: 16px;
    line-height: 26px;
    color: var(--primary--dark);
    text-decoration: none;
  }
  .secure-headline{
    font-weight: 400;
    font-size: 16px;
    line-height: 26px;
    color: #4B4E68;
  }
  .support__section{
    background: #FFFFFF;
    border: 1px solid #DADDF5;
    box-shadow: 0px 10px 30px rgba(22, 8, 49, 0.05);
    border-radius: 16px;
  }
  .support-about{
    padding: 35px 52px;
    display: flex;
    gap: 30px;
    align-items: center;
  }
  .support-text{
    display: flex;
    flex-direction: column;
  }
  .work-hours{
    font-weight: 600;
    font-size: 20px;
    line-height: 30px;
    color: var(--primary--dark);
  }
  .support-headline{
    font-weight: 400;
    font-size: 20px;
    line-height: 30px;
  }
  .submit__purchase-btn{
    margin-top: 70px;
    display: flex;
    flex-direction: column;
    gap: 31px;
    align-items: center;
  }
  .purchase{
    display: flex;
    align-items: center;
    gap: 8px;
    background: #050824;
    border-radius: 135.714px;
    color: #FFFFFF;
    padding: 22px 55px;
    font-weight: 600;
    font-size: 24.4286px;
    line-height: 33px;
    cursor: pointer;
  }
  .reject__purchase{
    font-weight: 600;
    font-size: 18px;
    line-height: 24px;
    color: #4B4E68;
    cursor: pointer;
    text-decoration: none;
  }
  .reject__purchase > a{
    text-decoration: none;
    color: #4B4E68;
  }
</style>

<style>
@media screen and (max-width: 576px){
  .page__wrapper{
    padding: 30px 16px !important;
    max-width: 100%;
  }
  .cart-item-slider{
    max-width: 100%;
  }
  .cart-item-img__middle{
    max-width: 100%;
  }
  .quantity-item__wrapper{
    padding: 40px 16px !important;
    max-width: 100%;
  }
  .quantity-text {
    padding: 15px 20px;
  }
  .description__section{
    max-width: 100%;
  }
  .support__security__section{
    margin-top: 30px;
  }
  .submit__purchase-btn{
    margin-top: 30px !important;
    width: 100% !important;
    justify-content: center;
    display: flex;
    flex-direction: column;
    align-items: unset;
  }
  .submit__purchase{
    min-width: 100%;
  }
  .purchase {
    width: 100% !important;
    justify-content: center;
  }
  .support__security__section{
    max-width: 100% !important;
  }
  .secure__section{
    padding: 16px 20px !important;
  }
}
</style>