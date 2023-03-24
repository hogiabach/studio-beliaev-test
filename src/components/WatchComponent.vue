<template>
  <div class="watchContainer">
    <p class="time">{{ time }}</p>
    <div class="buttonGroup">
      <button @click="start">start</button>
      <button @click="stop">stop</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      time: 0,
      interVal: null
    }
  },
  methods: {
    start() {
      if (!this.interVal) {
        this.interVal = setInterval(() => {
          this.time++
        }, 1000)
      }
      console.log(this.interVal)
    },
    stop() {
      clearInterval(this.interVal)
      this.interVal = null
    },
    reset() {
      this.time = 0
    }
  }
}
</script>

<style scoped>
.watchContainer {
  max-width: 225px;
  background-color: #9e9e9e;
  display: flex;
  flex-direction: column;
}

.time {
  padding-top: 20px;
  padding-bottom: 20px;
  text-align: center;
  border-bottom: 1px solid white;
  font-size: 1.375rem;
}
.buttonGroup {
  display: flex;
  flex-wrap: nowrap;
  align-items: center;
  justify-content: center;
  padding-top: 20px;
  padding-bottom: 20px;
  gap: 52px;
}
</style>
