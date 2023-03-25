<script>
import WatchComponent from './components/WatchComponent.vue'
import PlusWatchComponent from './components/PlusWatchComponent.vue'

export default {
  components: { WatchComponent, PlusWatchComponent },
  data() {
    return {
      quality: 0
    }
  },
  methods: {
    increase() {
      this.quality++
    }
  }
}
</script>

<template>
  <div class="div-wrap" v-for="i in quality" :key="i">
    <WatchComponent />
  </div>
  <div class="div-wrap" @click="increase">
    <PlusWatchComponent />
  </div>
</template>

<style scoped>
@font-face {
  font-family: 'Gotham-Pro';
  src: url('../public/font/gothampro.ttf') format('truetype');
}

.div-wrap {
  max-width: fit-content;
}
</style>
