<script setup>
import HeaderComponent from '@/components/HeaderComponent.vue'
import FooterComponent from '@/components/FooterComponent.vue'
import MainComponent from '@/components/MainComponent.vue'
// import { onMounted } from 'vue'

// const emit = defineEmits(['on-mount'])

// onMounted(() => {
//   console.log('Home component mounted.') // 確認ログ
//   emit('on-mount') // イベント名を小文字に変更
// })
</script>

<template>
  <div class="bgParallax">
    <video class="bgParallax-video" playsinline muted autoplay loop>
      <source src="../assets/imags/bg_movie.mp4" type="video/mp4" />
    </video>
  </div>
  <HeaderComponent />
  <MainComponent />
  <FooterComponent />
</template>

<style scoped>
.bgParallax {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: -1;
}
.bgParallax-video {
  width: 100%;
  height: 100vh;
  object-fit: cover;
}
</style>
