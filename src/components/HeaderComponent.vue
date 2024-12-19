<script setup>
import ButtonComponent from './ButtonComponent.vue'
import { ref, watch } from 'vue'
const audioPlayer = ref(null)
const soundFlag = ref(false)

watch(soundFlag, (newValue) => {
  if (audioPlayer.value) {
    if (newValue) {
      audioPlayer.value.muted = false
      audioPlayer.value.play().catch((err) => {
        console.error('Audio playback error:', err)
      })
    } else {
      audioPlayer.value.muted = true
      audioPlayer.value.pause()
    }
  }
})

function soundSwitch() {
  soundFlag.value = !soundFlag.value
}
</script>
<template>
  <header class="header">
    <div class="header-container">
      <div class="header-logo">Necopon games</div>
      <div class="header-link-container upper">
        <ul class="header-link">
          <li><a href="#story">story</a></li>
          <li><a href="#trailer">trailer</a></li>
        </ul>
        <ButtonComponent :btn-size="'btn-playnow-sm'" />
        <div class="header-sound upper" @click="soundSwitch">
          <span>sound {{ soundFlag ? 'ON' : 'OFF' }}</span>
          <span :class="[soundFlag ? 'soundOn' : 'soundOff isBolder']"></span>
          <audio ref="audioPlayer" autoplay loop :muted="!soundFlag">
            <source src="../assets/audio/cinematic-melody.mp3" type="audio/mpeg" />
          </audio>
        </div>
      </div>
    </div>
  </header>
</template>
<style scoped>
.header {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 10;
  width: 100%;
  height: 110px;
  background: linear-gradient(to bottom, black 20%, rgba(0, 0, 0, 0) 70%);
}
.header-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 28px 30px;
  width: 100%;
  color: var(--main-color);
  font-weight: bold;
}
.header-logo {
  font-size: 22px;
}
.header-link-container {
  position: relative;
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: relative;
  font-size: 16px;
}
.header-link {
  display: flex;
  justify-content: space-between;
  align-items: center;
  column-gap: 30px;
  list-style-type: none;
}

.header-sound {
  position: absolute;
  bottom: -42px;
  right: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  column-gap: 5px;
  color: #bfbfbf;
}
.soundOn {
  background-image: url(../assets/icon/soundOn.svg);
  background-repeat: no-repeat;
  background-size: cover;
  width: 25px;
  height: 25px;
}
.soundOff {
  background-image: url(../assets/icon/soundOff.svg);
  background-repeat: no-repeat;
  background-size: cover;
  width: 25px;
  height: 25px;
}
.isBolder {
  font-weight: 400;
}

@media screen and (max-width: 1023px) {
  .header {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 10;
    width: 100%;
    height: 90px;
    background: linear-gradient(to bottom, black 20%, rgba(0, 0, 0, 0) 90%);
  }
  .header-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 25px 25px;
    width: 100%;
    color: var(--main-color);
    font-weight: bold;
  }
  .header-logo {
    font-size: 18px;
  }
  .header-link-container {
    position: relative;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    font-size: 14px;
  }
  .header-link {
    display: flex;
    justify-content: space-between;
    align-items: center;
    column-gap: 25px;
    list-style-type: none;
  }

  .header-sound {
    position: absolute;
    bottom: -38px;
    right: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    column-gap: 5px;
    color: #bfbfbf;
  }
  .soundOn {
    background-image: url(../assets/icon/soundOn.svg);
    background-repeat: no-repeat;
    background-size: cover;
    width: 22px;
    height: 22px;
  }
  .soundOff {
    background-image: url(../assets/icon/soundOff.svg);
    background-repeat: no-repeat;
    background-size: cover;
    width: 22px;
    height: 22px;
  }
  .isBolder {
    font-weight: 400;
  }
}
@media screen and (max-width: 599px) {
  .header {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 10;
    width: 100%;
    height: 60px;
    background: linear-gradient(to bottom, black 20%, rgba(0, 0, 0, 0) 120%);
  }
  .header-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 22px 20px;
    width: 100%;
    color: var(--main-color);
    font-weight: bold;
  }
  .header-logo {
    font-size: 14px;
  }
  .header-link-container {
    position: relative;
    display: flex;
    justify-content: flex-end;
    align-items: center;
    position: relative;
    font-size: 12px;
  }
  .header-link {
    display: flex;
    justify-content: space-between;
    align-items: center;
    column-gap: 20px;
    list-style-type: none;
  }
  .header-sound {
    position: absolute;
    bottom: -35px;
    right: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    column-gap: 5px;
    color: #bfbfbf;
  }
  .soundOn {
    background-image: url(../assets/icon/soundOn.svg);
    background-repeat: no-repeat;
    background-size: cover;
    width: 20px;
    height: 20px;
  }
  .soundOff {
    background-image: url(../assets/icon/soundOff.svg);
    background-repeat: no-repeat;
    background-size: cover;
    width: 20px;
    height: 20px;
  }
  .isBolder {
    font-weight: 400;
  }
}
</style>
