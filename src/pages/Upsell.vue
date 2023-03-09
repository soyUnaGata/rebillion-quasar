<template>
  <div class="page__wrapper">
    <div class="cart-item-slider">
      <img class="cart-item-img__middle" src="../assets/sneakers_pink-bg-mid.png" alt="">
      <div class="slider-navigation">
        <img class="btn-left" src="../assets/btn-left.svg" alt="">
        <img class="btn-right" src="../assets/right-arrow-slider.svg" alt="">
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
  </div>
</template>
  
<script>
  import { defineComponent } from 'vue';
  
  export default defineComponent({
    name: 'PageUpsell'
  })
</script>

<style scoped>
  .page__wrapper{
    padding-top: 60px;
    padding-right: 565px;
    padding-left: 565px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .cart-item-img__middle{
    position: relative;
  }
  .slider-navigation{
    display: flex;
    width: 40px;
    height: 40px;
    position: absolute;
    gap: 642px;
    padding-left: 30px;
    top: 45%;
    cursor: pointer;
  }
  .quantity-item__wrapper{
    margin-top: 30px;
    background: #FFFFFF;
    border: 1px solid #DADDF5;
    box-shadow: 0px 10px 30px rgba(22, 8, 49, 0.05);
    border-radius: 16px;
    height: 225px;
    width: 790px;
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
    margin-top: 20px;
    margin-left: 125px;
    margin-right: 125px;
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
    width: 57px;
    height: 50px;
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
</style>