<template>
  <div class="countdown">
    <h4 class="countdown-text"> 🔥 Your cart is reserved for 
      <span>10:00</span> 
      minutes
    </h4>
    <div class="countdown-hms">
      <p class="hms hours">00</p>
      <p class="divide-dots">:</p>
      <p class="hms minutes">{{ minutes.toString().padStart(2, '0') }}</p>
      <p class="divide-dots separator">:</p>
      <p class="hms seconds blink">{{ seconds.toString().padStart(2, '0') }}</p>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'CountDown',
  data(){
    return {
      minutes: 10,
      seconds: 0,
      timer: null
    }
  },
  methods:{
    tick(){
      if (this.seconds > 0) {
        this.seconds--;
        return;
      } 
      
      if (this.minutes > 0) {
        this.minutes--;
        this.seconds = 59;
        return;
      }

      clearInterval(this.timer);
      alert('Time is up!');
    }
  },
  created() {
    this.timer = setInterval(this.tick, 1000);
  },
  unmounted(){
    clearInterval(this.timer);
  }
});
</script>

<style>
.separator {
  animation: blink 1s infinite;
}

@keyframes blink {
  50% {
    opacity: 0;
  }
}
.countdown{
  margin-top: 50px;
  background-color: var(--bg--countdown);
  border-radius: 32px;
  width: 540px;
  padding: 30px;
  max-width: 100%;
  color: var(--primary--dark);
}
.countdown-text{
  font-style: normal;
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
  align-items: center;
  width: 180px;
  max-width: 100%;
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
