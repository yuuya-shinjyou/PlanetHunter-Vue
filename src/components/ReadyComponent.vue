<script setup>
import ButtonComponent from './ButtonComponent.vue'
</script>

<template>
  <div class="ready">
    <h1 class="ready-title upper">are you ready to <br class="sp-break" />fight?</h1>
    <ButtonComponent :btn-size="'btn-playnow-mid'" />
  </div>
</template>

<style scoped>
.ready {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 350px;
}
.ready-title {
  font-size: 64px;
  font-weight: bold;
  line-height: 70px;
  letter-spacing: 0.05rem;
  margin-bottom: 20px;
}
.sp-break {
  display: none;
}
@media screen and (max-width: 1023px) {
  .ready {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 350px;
  }
  .ready-title {
    text-align: center;
    font-size: 55px;
    font-weight: bold;
    line-height: 55px;
    letter-spacing: 0.05rem;
    margin-bottom: 20px;
  }
  .sp-break {
    display: block;
  }
}
@media screen and (max-width: 599px) {
  .ready {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 275px;
  }
  .ready-title {
    text-align: center;
    font-weight: bold;
    font-size: 30px;
    line-height: 30px;
    letter-spacing: 0.05rem;
    margin-bottom: 20px;
  }
  .sp-break {
    display: block;
  }
}
</style>
