<script setup>
const btnSize = defineProps({
  btnSize: {
    type: String,
    Required: true,
    default: '',
  },
})
</script>

<template>
  <button :class="btnSize.btnSize" class="upper">play now</button>
</template>

<style scoped>
.btn-playnow-sm {
  padding: 15px 40px;
  margin-left: 30px;
  background-color: var(--main-color);
  color: black;
  font-size: 15px;
  font-weight: bold;
  line-height: 15px;
  letter-spacing: 0.05rem;
}
.btn-playnow-mid {
  padding: 20px 65px;
  background-color: var(--main-color);
  color: black;
  font-size: 18px;
  font-weight: bold;
  line-height: 20px;
  letter-spacing: 0.05rem;
}
.btn-playnow-lg {
  display: none;
}
@media screen and (max-width: 1023px) {
  .btn-playnow-sm {
    padding: 12px 27px;
    margin-left: 30px;
    background-color: var(--main-color);
    color: black;
    font-size: 12px;
    font-weight: bold;
    line-height: 15px;
    letter-spacing: 0.05rem;
  }
  .btn-playnow-mid {
    padding: 15px 43px;
    background-color: var(--main-color);
    color: black;
    font-size: 15px;
    font-weight: bold;
    line-height: 18px;
    letter-spacing: 0.05rem;
  }
  .btn-playnow-lg {
    display: none;
  }
}
@media screen and (max-width: 599px) {
  .btn-playnow-sm {
    display: none;
  }
  .btn-playnow-mid {
    padding: 18px 40px;
    background-color: var(--main-color);
    color: black;
    font-size: 16px;
    font-weight: bold;
    line-height: 16px;
    letter-spacing: 0.05rem;
  }
  .btn-playnow-lg {
    display: block;
    width: 100%;
    padding: 20px;
    background-color: var(--main-color);
    color: black;
    font-size: 16px;
    font-weight: bold;
    line-height: 16px;
    letter-spacing: 0.05rem;
    text-align: center;
  }
}
</style>
