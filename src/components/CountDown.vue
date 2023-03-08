<template>
  <div class="countdown">
    <p class="countdown-text"> 🔥 Your cart is reserved for 
      <span>10:00</span> 
      minutes
    </p>
    <div class="countdown-hms">
      <p class="hms hours">00</p>
      <p class="divide-dots">:</p>
      <p class="hms minutes">09</p>
      <p class="divide-dots">:</p>
      <p class="hms seconds">39</p>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'CountDown'  
})
</script>

<style scoped>
.countdown{
  margin-top: 50px;
  background-color: var(--bg--countdown);
  border-radius: 32px;
  width: 540px;
  height: 139px;
  color: var(--primary--dark);
}
.countdown-text{
  font-style: normal;
  padding-top: 30px;
  padding-left: 30px;
  font-weight: 500;
  font-size: 18px;
  line-height: 27px;
  color: var(--primary--dark);
}
.countdown-text > span {
  font-weight: 900;
}
.countdown-hms{
  margin-top: 15px;
  display: flex;
  gap: 8px;
  margin-left: 30px;
  align-items: center;
  width: 180px;
}
.hms{
  width: 46px;
  height: 37px;
  border-radius: 12px;
  background-color: var(--bg--shipping);
  align-items: center;
  display: flex;
  justify-content: center;
  font-weight: 500;
  font-size: 18px;
  line-height: 27px;
  color: var(--primary--dark);
}
.divide-dots{
  font-weight: 500;
}
</style>
