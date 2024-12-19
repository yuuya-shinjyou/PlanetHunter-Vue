<script setup>
// import { ref } from 'vue'
import { RouterView } from 'vue-router'

// ローディング状態を管理
// const isLoading = ref(true)

// Home がマウントされたときに呼ばれる関数
// const handleIsLoading = () => {
//   isLoading.value = false // マウント完了後にローディングを非表示
//   console.log('Home component is mounted:', isLoading.value)
// }
</script>

<template>
  <div>
    <!-- ローディング画面
    <div v-if="isLoading" style="color: red; font-size: 50px">
      <h1>Loading...</h1>
    </div> -->
    <!-- コンテンツ -->
    <!-- <RouterView @on-mount="isLoading = false"></RouterView> -->
    <RouterView></RouterView>
  </div>
</template>

<style scoped>
/* ローディング */
/* .loading {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: var(--main-color);
  background-color: black;
} */
</style>
