<template>
  <div class="notfound">
    <h1 class="notfound-title">おおっと！</h1>
    <p class="notfound-subtitle upper">404 - page not found</p>
    <span class="notfound-content">
      お探しのページは名前が変更されたか、削除された可能性があります。
    </span>
  </div>
</template>

<style scoped>
.notfound {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  row-gap: 5px;
  color: var(--main-color);
  background-color: black;
  overflow: hidden;
}
.notfound-title {
  font-size: 150px;
  font-weight: 900;
  letter-spacing: 0.7rem;
}
.notfound-subtitle {
  font-size: 50px;
  font-weight: bold;
  letter-spacing: 0.2rem;
}
.notfound-content {
  font-size: 16px;
  letter-spacing: 0.2rem;
}
</style>
