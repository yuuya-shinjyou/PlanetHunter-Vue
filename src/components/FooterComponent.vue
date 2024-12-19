<script setup>
import ButtonComponent from './ButtonComponent.vue'
import { ref } from 'vue'
let count = ref(0)
</script>
<template>
  <footer class="footer">
    <div class="footer-link">
      <button class="footer-iine" href="" @click="count++">いいね！ {{ count }}</button>
      <a class="footer-share" href="">シェアする</a>
      <div class="footer-xpost">
        <a
          href="https://twitter.com/share?ref_src=twsrc%5Etfw"
          class="twitter-share-button"
          data-show-count="false"
          >Tweet</a
        >
      </div>

      <div class="footer-line">
        <div
          class="line-it-button"
          data-lang="ja"
          data-type="share-b"
          data-env="REAL"
          data-url="http://aaaaa"
          data-color="default"
          data-size="small"
          data-count="false"
          data-ver="3"
          style="display: none"
        ></div>
      </div>
    </div>
    <div class="footer-logName">©Necopon games</div>
    <ButtonComponent :btn-size="'btn-playnow-lg'" />
  </footer>
</template>
<style scoped>
.footer {
  position: relative;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 40px 30px;
  background-color: black;
}
.footer::before {
  position: absolute;
  content: '';
  top: -38px;
  right: 0;
  z-index: 1;
  width: 430px;
  height: 40px;
  background-image: url(../assets/imags/bg-line-bottom-black.svg);
  background-repeat: no-repeat;
}
.footer-link {
  display: flex;
  align-items: center;
  column-gap: 15px;
}
.footer-iine,
.footer-share {
  min-width: 100px;
  text-align: center;
  padding: 2px 0px;
  background-color: #1877f2;
  border-radius: 5px;
  letter-spacing: 0.05rem;
}
.footer-xpost {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 70px;
  height: 80px;
}
.footer-line {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 45px;
  height: 45px;
}
.footer-logName {
  font-size: 14px;
  font-weight: bold;
  line-height: 14px;
  letter-spacing: 0.05rem;
}
@media screen and (max-width: 1023px) {
  .footer {
    position: relative;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 38px 25px;
    background-color: black;
  }
  .footer::before {
    position: absolute;
    content: '';
    top: -33px;
    right: 0;
    z-index: 1;
    width: 300px;
    height: 35px;
    background-image: url(../assets/imags/bg-line-bottom-black.svg);
    background-repeat: no-repeat;
  }
  .footer-link {
    display: flex;
    align-items: center;
    column-gap: 10px;
  }
  .footer-iine,
  .footer-share {
    min-width: 100px;
    text-align: center;
    padding: 3px 0px;
    background-color: #1877f2;
    border-radius: 4px;
    letter-spacing: 0.05rem;
  }
  .footer-xpost {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 70px;
    height: 80px;
  }
  .footer-line {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 40px;
    height: 40px;
  }
  .footer-logName {
    font-size: 13px;
    font-weight: bold;
    line-height: 14px;
    letter-spacing: 0.05rem;
  }
}
@media screen and (max-width: 599px) {
  .footer {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 38px 20px 19px;
    background-color: black;
  }
  .footer::before {
    position: absolute;
    content: '';
    top: -29px;
    right: 0;
    z-index: 1;
    width: 200px;
    height: 30px;
    background-image: url(../assets/imags/bg-line-bottom-black.svg);
    background-repeat: no-repeat;
  }
  .footer-link {
    display: flex;
    justify-content: space-between;
    align-items: center;
    column-gap: 5px;
    width: 100%;
    margin-bottom: 30px;
    font-size: 12px;
  }
  .footer-iine,
  .footer-share {
    width: 30%;
    min-width: 70px;
    text-align: center;
    padding: 5px 0px;
    background-color: #1877f2;
    border-radius: 3px;
    letter-spacing: 0.05rem;
  }
  .footer-xpost {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0px 4px;
  }
  .footer-line {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 35px;
    height: 35px;
  }
  .footer-logName {
    font-size: 11px;
    font-weight: bold;
    line-height: 14px;
    letter-spacing: 0.05rem;
    margin-bottom: 44px;
  }
}
</style>
