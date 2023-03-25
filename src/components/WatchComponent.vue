<template>
  <div class="container">
    <p
      :style="{
        borderBottom: interVal ? '1px solid white' : '1px solid #9E9E9E',
        color: interVal ? 'white' : '#9E9E9E'
      }"
      class="time"
    >
      {{ getTime }}
    </p>
    <div class="buttonGroup">
      <component v-if="interVal" :is="'PauseIcon'" :color="'#ffffff'" :handleClick="stop" />
      <component v-else :is="'PlayIcon'" :color="'#9E9E9E'" :handleClick="start" />
      <ResetIcon :color="interVal ? '#ffffff' : '#9E9E9E'" :handleClick="reset" />
    </div>
  </div>
</template>

<script>
import PauseIcon from './icons/PauseIcon.vue'
import PlayIcon from './icons/PlayIcon.vue'
import ResetIcon from './icons/ResetIcon.vue'

export default {
  components: { PauseIcon, PlayIcon, ResetIcon },
  data() {
    return {
      second: 0,
      interVal: null
    }
  },
  computed: {
    getTime() {
      let hours = Math.floor(this.second / 3600)
        .toString()
        .padStart(1, '0')
      let minute = Math.floor((this.second % 3600) / 60)
        .toString()
        .padStart(1, '0')
      let second = (this.second % 60).toString().padStart(1, '0')
      return this.second < 60
        ? second
        : this.second >= 60 && this.second < 3600
        ? `${minute}:${second}`
        : `${hours}:${minute}:${second}`
    }
  },
  methods: {
    start() {
      if (!this.interVal) {
        this.interVal = setInterval(() => {
          this.second++
        }, 1000)
      }
    },
    stop() {
      clearInterval(this.interVal)
      this.interVal = null
    },
    reset() {
      this.second = 0
      clearInterval(this.interVal)
      this.interVal = null
    }
  }
}
</script>

<style scoped>
.container {
  max-width: 225px;
  background-color: #696969;
  display: flex;
  flex-direction: column;
}

.time {
  padding-top: 20px;
  padding-bottom: 20px;
  text-align: center;
  font-size: 1.375rem;
  font-family: 'Gotham-Pro', Helvetica, Arial;
}
.buttonGroup {
  display: flex;
  flex-wrap: nowrap;
  align-items: center;
  justify-content: center;
  column-gap: 52px;
  padding: 20px 70px;
}
</style>
