<script setup>
import ButtonComponent from './ButtonComponent.vue'
import ReadyComponent from './ReadyComponent.vue'
</script>

<template>
  <main class="main">
    <section class="catch-container">
      <div class="catch">
        <p class="catch-subtitle">VR GAME</p>
        <h1 class="catch-title">
          Planet<br />
          Hunters
        </h1>
        <p class="catch-tagline">惑星を奪還せよ</p>
        <ButtonComponent :btn-size="'btn-playnow-mid'" />
      </div>

      <div class="scroll">
        <span>Scroll</span>
        <div class="scroll-line"></div>
      </div>

      <div class="notice-container">
        <div class="notice">
          <div class="notice-item">
            <time datetime="2030.02.20">2030.02.20</time>
            <span> バージョン5.6リリース：アバター・アイ </span>
          </div>
        </div>
      </div>
    </section>

    <section id="story" class="story">
      <div class="story-bgimg">
        <div class="story-synopsis">
          <div class="story-content">
            <div class="story-text">
              <h1 class="story-title">STORY</h1>
              <p class="story-subtitle">
                奪われた故郷の星を取り戻せ<br />
                壮大なSFファンタジー
              </p>
              <p class="story-detail">
                銀河歴222年、惑星ネコチャンは、ボスネコ将軍の率いる軍の反乱により完全に制圧された。将軍の側近マンチカンは軍政府に従わない人間を辺境の星ニャゴーへ強制的に追放。食料や資源の乏しいニャゴーでは多くの難民が発生し飢餓に苦しんでいた。ニャゴーのスラム街で育った孤児の姉弟がいた。姉のミケと弟のタマは母親をボスネコ将軍に殺された事実を知る。母の復讐のため、そして故郷の惑星ネコチャンを奪還すべく、ミケとタマはいま行動に出る！
              </p>
            </div>
            <div>
              <img class="story-img" src="../assets/imags/story01.webp" alt="" />
            </div>
          </div>
          <div class="story-content">
            <div class="story-text">
              <p class="story-subtitle">
                隠された陰謀を暴け<br />
                衝撃的な事実に驚愕
              </p>
              <p class="story-detail">
                ミケとタマはネコジャラシ作戦により軍政府の最新鋭の小型船チュールを奪うことに成功。チュールのハイテンションワープ星間航行により惑星ネコチャンへあとわずか３時間で到着という時、小惑星帯アビシニアンで謎の救難信号を受信する。意外にも信号の発信源はボスネコ将軍だった。彼は今にも絶えそうなかすれた声で「私はおまえたちミケとタマの父親なのだ」と語る。その瞬間、ミケとタマの育ての親同然で仲間のはずのホワイトオッドアイがタマの背中を刀で切り裂いたのだった......
              </p>
            </div>
            <div>
              <img class="story-img" src="../assets/imags/story02.webp" alt="" />
            </div>
          </div>
        </div>
      </div>
    </section>

    <ReadyComponent />

    <section id="trailer" class="trailer">
      <div class="trailer-content">
        <h1 class="trailer-title">TRAILER</h1>
        <iframe
          class="trailer-youtube"
          src="https://www.youtube.com/embed/RO_RRKTYzUY?si=ZR503-7v3XwbkfdU"
          title="YouTube video player"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          referrerpolicy="strict-origin-when-cross-origin"
          allowfullscreen
        ></iframe>
      </div>
    </section>

    <ReadyComponent />
  </main>
</template>

<style scoped>
/* キャッチセクション */
.catch-container {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  /* align-items: center; */
  min-height: 100vh;
  min-width: 100%;
}
.catch {
  /* transform: translateX(-50%); */
  margin-left: 10%;
}
.catch-subtitle {
  font-weight: bold;
  font-size: 32px;
  line-height: 32px;
  letter-spacing: 0.2rem;
  margin-bottom: 30px;
}
.catch-title {
  font-weight: 600;
  font-size: 140px;
  line-height: 126px;
  letter-spacing: 0.05rem;
  margin-bottom: 10px;
}
.catch-tagline {
  font-weight: 500;
  font-size: 34px;
  line-height: 34px;
  letter-spacing: 1rem;
  margin-bottom: 50px;
}
/* スクロール */
.scroll {
  position: absolute;
  bottom: 20px;
  left: 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  font-weight: bold;
  font-size: 13px;
  line-height: 44.5px;
  color: var(--main-color);
  transform: rotate(90deg);
}
.scroll-line {
  position: relative;
  min-width: calc(var(--scroll-linelength) * 5);
  border: 1px solid var(--main-color);
}
.scroll-line::after {
  content: '';
  display: block;
  position: absolute;
  top: calc(var(--scroll-linelength) / 2 * -1);
  width: var(--scroll-linelength);
  height: var(--scroll-linelength);
  border-radius: 50%;
  background-color: var(--main-color);
  opacity: 0;
  animation: 1.7s ease-in-out infinite scrolling;
}
@keyframes scrolling {
  0% {
    left: calc(var(--scroll-linelength) / 2 * -1);
    opacity: 0;
  }
  20% {
    opacity: 1;
  }
  80% {
    opacity: 1;
  }
  100% {
    left: calc(var(--scroll-linelength) * 4 + 5px);
    opacity: 0;
  }
}

/* お知らせバー */
.notice-container {
  position: absolute;
  right: 30px;
  bottom: 50px;
  width: 360px;
  border: 1px solid var(--main-color);
  background-color: black;
  overflow: hidden;
  padding: 8px 0px;
}

.notice {
  display: flex;
  flex-shrink: 0;
  column-gap: 20px;
  animation: marquee-left 10s linear infinite;
}

.notice-item {
  display: flex;
  column-gap: 15px;
  white-space: nowrap;
  color: white; /* 文字色 */
}

@keyframes marquee-left {
  0% {
    transform: translateX(100%); /* 右端から始める */
  }
  100% {
    transform: translateX(-100%); /* 左端へ移動 */
  }
}

/* Storyセクション */
.story {
  position: relative;
}
.story::before {
  position: absolute;
  content: '';
  top: -38px;
  right: 0px;
  z-index: 1;
  width: 430px;
  height: 40px;
  background-image: url(../assets/imags/bg-line-bottom-black.svg);
  background-repeat: no-repeat;
}
.story::after {
  position: absolute;
  content: '';
  bottom: -38px;
  left: 0px;
  z-index: 1;
  width: 430px;
  height: 40px;
  background-image: url(../assets/imags/bg-line-top-black.svg);
  background-repeat: no-repeat;
}

.story-bgimg {
  padding: 140px 160px;
  background-image: url(../assets/imags/bg_story.webp);
  background-position: center center;
  background-size: cover;
  background-repeat: no-repeat;
}
.story-synopsis {
  display: flex;
  flex-direction: column;
  row-gap: 85px;
}
.story-content {
  display: flex;
  align-items: center;
  column-gap: 80px;
  max-width: 1100px;
  width: 100%;
}
.story-content:nth-of-type(even) {
  flex-direction: row-reverse;
}
.story-text {
  flex: 7;
}
.story-title {
  position: relative;
  color: var(--main-color);
  font-size: 80px;
  font-weight: bolder;
  line-height: 80px;
  letter-spacing: 0.05rem;
  margin-bottom: 70px;
}
.story-title::after {
  position: absolute;
  content: '';
  bottom: -30px;
  left: 0;
  width: 80px;
  border: 4px solid var(--main-color);
}
.story-subtitle {
  min-width: 320px;
  font-size: 32px;
  font-weight: 400;
  line-height: 48px;
  letter-spacing: 0.05rem;
  margin-bottom: 30px;
}
.story-detail {
  font-size: 16px;
  font-weight: 400;
  line-height: 28.8px;
  letter-spacing: 0.05rem;
}
.story-img {
  max-width: 435px;
  width: 100%;
  background-size: cover;
  box-shadow: 10px 10px 0px 0px var(--main-color);
  transform: skew(-5deg, 0deg);
}
.story-content:nth-of-type(even) .story-img {
  box-shadow: -10px 10px 0px 0px var(--main-color);
  transform: skew(5deg, 0deg);
}
.trailer {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 110px 165px;
  background-color: var(--main-color);
}
.trailer::before {
  position: absolute;
  content: '';
  top: -38px;
  right: 0px;
  z-index: 1;
  width: 430px;
  height: 40px;
  background-image: url(../assets/imags/bg-line-bottom-color.svg);
  background-repeat: no-repeat;
}
.trailer::after {
  position: absolute;
  content: '';
  bottom: -38px;
  left: 0px;
  z-index: 1;
  width: 430px;
  height: 40px;
  background-image: url(../assets/imags/bg-line-top-color.svg);
  background-repeat: no-repeat;
}
.trailer-content {
  width: 100%;
}
.trailer-title {
  position: relative;
  color: black;
  font-size: 80px;
  font-weight: bolder;
  line-height: 80px;
  letter-spacing: 0.05rem;
  margin-bottom: 70px;
}
.trailer-title::after {
  position: absolute;
  content: '';
  bottom: -30px;
  left: 0;
  width: 80px;
  border: 4px solid black;
}
.trailer-youtube {
  width: 100%;
  aspect-ratio: 16 / 9;
}

@media screen and (max-width: 1023px) {
  /* キャッチセクション */
  .catch-container {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    min-height: 100vh;
    min-width: 100%;
  }
  .catch {
    margin-left: 10%;
  }
  .catch-subtitle {
    font-weight: bold;
    font-size: 22px;
    line-height: 22px;
    letter-spacing: 0.2rem;
    margin-bottom: 20px;
  }
  .catch-title {
    font-weight: 600;
    font-size: 90px;
    line-height: 90px;
    letter-spacing: 0.05rem;
    margin-bottom: 8px;
  }
  .catch-tagline {
    font-weight: 500;
    font-size: 25px;
    line-height: 28px;
    letter-spacing: 0.8rem;
    margin-bottom: 40px;
  }
  /* スクロール */
  .scroll {
    position: absolute;
    bottom: 20px;
    left: 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-weight: bold;
    font-size: 13px;
    line-height: 44.5px;
    color: var(--main-color);
    transform: rotate(90deg);
  }
  .scroll-line {
    position: relative;
    min-width: calc(var(--scroll-linelength) * 5);
    border: 1px solid var(--main-color);
  }
  .scroll-line::after {
    content: '';
    display: block;
    position: absolute;
    top: calc(var(--scroll-linelength) / 2 * -1);
    width: var(--scroll-linelength);
    height: var(--scroll-linelength);
    border-radius: 50%;
    background-color: var(--main-color);
    opacity: 0;
    animation: 1.7s ease-in-out infinite scrolling;
  }
  @keyframes scrolling {
    0% {
      left: calc(var(--scroll-linelength) / 2 * -1);
      opacity: 0;
    }
    20% {
      opacity: 1;
    }
    80% {
      opacity: 1;
    }
    100% {
      left: calc(var(--scroll-linelength) * 4 + 5px);
      opacity: 0;
    }
  }

  /* お知らせバー */
  .notice-container {
    position: absolute;
    right: 25px;
    bottom: 50px;
    width: 280px;
    height: 30px;
    border: 1px solid var(--main-color);
    background-color: black;
    overflow: hidden;
    padding: 8px 0px;
  }

  .notice {
    display: flex;
    flex-shrink: 0;
    column-gap: 20px;
    animation: marquee-left 10s linear infinite;
  }

  .notice-item {
    display: flex;
    column-gap: 15px;
    white-space: nowrap;
    color: white; /* 文字色 */
  }

  @keyframes marquee-left {
    0% {
      transform: translateX(100%); /* 右端から始める */
    }
    100% {
      transform: translateX(-100%); /* 左端へ移動 */
    }
  }
  /* Storyセクション */
  .story {
    position: relative;
  }
  .story::before {
    position: absolute;
    content: '';
    top: -33px;
    right: 0px;
    z-index: 1;
    width: 300px;
    height: 35px;
    background-image: url(../assets/imags/bg-line-bottom-black.svg);
    background-repeat: no-repeat;
  }
  .story::after {
    position: absolute;
    content: '';
    bottom: -33px;
    left: 0px;
    z-index: 1;
    width: 300px;
    height: 35px;
    background-image: url(../assets/imags/bg-line-bottom-black.svg);
    background-repeat: no-repeat;
    transform: rotate(180deg);
  }

  .story-bgimg {
    padding: 80px;
    background-image: url(../assets/imags/bg_story.webp);
    background-position: center center;
    background-size: cover;
    background-repeat: no-repeat;
  }
  .story-synopsis {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    row-gap: 80px;
  }
  .story-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    row-gap: 30px;
    max-width: 1100px;
    width: 100%;
  }
  .story-content:nth-of-type(even) {
    flex-direction: column;
  }
  .story-text {
    flex: 7;
  }
  .story-title {
    position: relative;
    color: var(--main-color);
    font-size: 55px;
    font-weight: bolder;
    line-height: 55px;
    letter-spacing: 0.05rem;
    margin-bottom: 60px;
  }
  .story-title::after {
    position: absolute;
    content: '';
    bottom: -20px;
    left: 0;
    width: 80px;
    border: 3px solid var(--main-color);
  }
  .story-subtitle {
    font-size: 28px;
    font-weight: 400;
    line-height: 40px;
    letter-spacing: 0.05rem;
    margin-bottom: 30px;
  }
  .story-detail {
    font-size: 14px;
    font-weight: 400;
    line-height: 24px;
    letter-spacing: 0.05rem;
  }
  .story-img {
    flex: 3;
    max-width: 400px;
    width: 900%;
    background-size: cover;
    box-shadow: 10px 10px 0px 0px var(--main-color);
    transform: skew(0deg, 0deg);
  }
  .story-content:nth-of-type(even) .story-img {
    box-shadow: -10px 10px 0px 0px var(--main-color);
    transform: skew(0deg, 0deg);
  }

  .trailer {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 60px 80px;
    background-color: var(--main-color);
  }
  .trailer::before {
    position: absolute;
    content: '';
    top: -33px;
    right: 0px;
    z-index: 1;
    width: 300px;
    height: 35px;
    background-image: url(../assets/imags/bg-line-bottom-color.svg);
    background-repeat: no-repeat;
  }
  .trailer::after {
    position: absolute;
    content: '';
    bottom: -33px;
    left: 0px;
    z-index: 1;
    width: 300px;
    height: 35px;
    background-image: url(../assets/imags/bg-line-bottom-color.svg);
    background-repeat: no-repeat;
    transform: rotate(180deg);
  }
  .trailer-content {
    width: 100%;
  }
  .trailer-title {
    position: relative;
    color: black;
    font-size: 55px;
    font-weight: bolder;
    line-height: 55px;
    letter-spacing: 0.05rem;
    margin-bottom: 60px;
  }
  .trailer-title::after {
    position: absolute;
    content: '';
    bottom: -25px;
    left: 0;
    width: 80px;
    border: 3px solid black;
  }
  .trailer-youtube {
    width: 100%;
    aspect-ratio: 16 / 9;
  }
}
@media screen and (max-width: 599px) {
  /* キャッチセクション */
  .catch-container {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    min-height: 100vh;
    min-width: 100%;
  }
  .catch {
    margin-left: 10%;
  }
  .catch-subtitle {
    font-weight: bold;
    font-size: 22px;
    line-height: 22px;
    letter-spacing: 0.2rem;
    margin-bottom: 20px;
  }
  .catch-title {
    font-weight: 600;
    font-size: 70px;
    line-height: 68.4px;
    letter-spacing: 0.05rem;
    margin-bottom: 10px;
  }
  .catch-tagline {
    font-weight: 500;
    font-size: 22px;
    line-height: 29px;
    letter-spacing: 0.6rem;
    margin-bottom: 30px;
  }
  /* スクロール */
  .scroll {
    position: absolute;
    bottom: 20px;
    left: 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-weight: bold;
    font-size: 13px;
    line-height: 44.5px;
    color: var(--main-color);
    transform: rotate(90deg);
  }
  .scroll-line {
    position: relative;
    min-width: calc(var(--scroll-linelength) * 5);
    border: 1px solid var(--main-color);
  }
  .scroll-line::after {
    content: '';
    display: block;
    position: absolute;
    top: calc(var(--scroll-linelength) / 2 * -1);
    width: var(--scroll-linelength);
    height: var(--scroll-linelength);
    border-radius: 50%;
    background-color: var(--main-color);
    opacity: 0;
    animation: 1.7s ease-in-out infinite scrolling;
  }
  @keyframes scrolling {
    0% {
      left: calc(var(--scroll-linelength) / 2 * -1);
      opacity: 0;
    }
    20% {
      opacity: 1;
    }
    80% {
      opacity: 1;
    }
    100% {
      left: calc(var(--scroll-linelength) * 4 + 5px);
      opacity: 0;
    }
  }

  /* お知らせバー */
  .notice-container {
    position: absolute;
    right: 20px;
    bottom: 50px;
    width: 200px;
    height: 27px;
    border: 1px solid var(--main-color);
    background-color: black;
    overflow: hidden;
    padding: 8px 0px;
  }

  .notice {
    display: flex;
    flex-shrink: 0;
    column-gap: 20px;
    animation: marquee-left 10s linear infinite;
  }

  .notice-item {
    display: flex;
    column-gap: 15px;
    white-space: nowrap;
    color: white; /* 文字色 */
  }

  @keyframes marquee-left {
    0% {
      transform: translateX(100%); /* 右端から始める */
    }
    100% {
      transform: translateX(-100%); /* 左端へ移動 */
    }
  }

  /* Storyセクション */
  .story {
    position: relative;
    width: 100%;
  }
  .story::before {
    position: absolute;
    content: '';
    top: -28px;
    right: 0px;
    z-index: 1;
    width: 200px;
    height: 30px;
    background-image: url(../assets/imags/bg-line-bottom-black.svg);
    background-repeat: no-repeat;
  }
  .story::after {
    position: absolute;
    content: '';
    bottom: -28px;
    right: 0px;
    z-index: 1;
    width: 200px;
    height: 30px;
    background-image: url(../assets/imags/bg-line-bottom-black.svg);
    background-repeat: no-repeat;
    transform: rotate(180deg);
    /* topは何故か真四角で表示されるため */
  }

  .story-bgimg {
    padding: 50px 20px;
    background-image: url(../assets/imags/bg_story.webp);
    background-position: center center;
    background-size: cover;
    background-repeat: no-repeat;
  }
  .story-synopsis {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    row-gap: 53px;
  }
  .story-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    row-gap: 30px;
    width: 100%;
  }
  .story-content:nth-child(even) {
    flex-direction: column;
  }
  .story-title {
    position: relative;
    color: var(--main-color);
    font-size: 50px;
    font-weight: bolder;
    line-height: 50px;
    letter-spacing: 0.05rem;
    margin-bottom: 45px;
  }
  .story-title::after {
    position: absolute;
    content: '';
    bottom: -15px;
    left: 0;
    width: 60px;
    border: 2px solid var(--main-color);
  }
  .story-subtitle {
    min-width: 260px;

    font-size: 24px;
    font-weight: 400;
    line-height: 32px;
    letter-spacing: 0.05rem;
    margin-bottom: 20px;
  }
  .story-detail {
    font-size: 15px;
    font-weight: 400;
    line-height: 27px;
    letter-spacing: 0.05rem;
  }
  .story-img {
    width: 100%;
    background-size: cover;
    box-shadow: 10px 10px 0px 0px var(--main-color);

    transform: skew(-0deg, 0deg);
  }
  .story-content:nth-child(even) .story-img {
    box-shadow: -10px 10px 0px 0px var(--main-color);
    transform: skew(0deg, 0deg);
  }

  .trailer {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 50px 24px;
    background-color: var(--main-color);
  }
  .trailer::before {
    position: absolute;
    content: '';
    top: -28px;
    right: 0px;
    z-index: 1;
    width: 200px;
    height: 30px;
    background-image: url(../assets/imags/bg-line-bottom-color.svg);
    background-repeat: no-repeat;
  }
  .trailer::after {
    position: absolute;
    content: '';
    bottom: -28px;
    left: 0px;
    z-index: 1;
    width: 200px;
    height: 30px;
    background-image: url(../assets/imags/bg-line-bottom-color.svg);
    background-repeat: no-repeat;
    transform: rotate(180deg);
    /* topは真四角が表示されるため */
  }
  .trailer-content {
    width: 100%;
  }
  .trailer-title {
    position: relative;
    color: black;
    font-size: 50px;
    font-weight: bolder;
    line-height: 50px;
    letter-spacing: 0.05rem;
    margin-bottom: 45px;
  }
  .trailer-title::after {
    position: absolute;
    content: '';
    bottom: -15px;
    left: 0;
    width: 60px;
    border: 2px solid black;
  }
  .trailer-youtube {
    width: 100%;
    aspect-ratio: 16 / 9;
  }
}
</style>
