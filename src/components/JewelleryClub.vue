<template>
     <div class="jewellery__club-about">
    <span class="jewellery__club-headline">The ultimate jewellery club</span>
    <span class="jewellery__club-description">Ornare rhoncus nunc ut felis. Faucibus dolor at ultrices tincidunt. Pulvinar sed justo et viverra pellentesque.</span>

    <div class="jewellery__club-advances">
      <div class="list__of__advnces">
        <img src="../assets/ok__sign.svg" alt="">
        <span>Extra 10$ off!</span>
      </div>
      <div class="list__of__advnces">
        <img src="../assets/ok__sign.svg" alt="">
        <span>Free shipping on marked club items!</span>
      </div>
      <div class="list__of__advnces">
        <img src="../assets/ok__sign.svg" alt="">
        <span>Free returns on marked club items!</span>
      </div>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'JewelleryClub'
})
</script>

<style scoped>
.jewellery__club-about{
  width: 449px;
  height: 245px;
  background: #FFFFFF;
  border: 1px solid #D6D8EA;
  border-radius: 32px;
  display: flex;
  flex-direction: column;
  margin-top: 15px;
  padding-left: 30px;
  padding-top: 30px;
}
.jewellery__club-headline{
  font-weight: 600;
  font-size: 18px;
  line-height: 27px;
  color: var(--primary--dark);
}
.jewellery__club-description{
  font-weight: 400;
  font-size: 14px;
  line-height: 24px;
  color: #4B4E68;
  padding-top: 10px;
}
.jewellery__club-advances{
  padding-top: 20px;
  display: flex;
  flex-direction: column;
  gap: 4px;
}
.list__of__advnces{
  display: flex;
  gap: 10px;
  align-items: center;
  font-weight: 400;
  font-size: 14px;
  line-height: 24px;
  color: #4B4E68;
}
</style>