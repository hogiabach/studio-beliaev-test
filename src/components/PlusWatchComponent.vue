<script>
import PlusIcon from './icons/PlusIcon.vue'
export default {
  components: { PlusIcon }
}
</script>

<template>
  <div @click="increase" class="plusContainer"><PlusIcon /></div>
</template>

<style scoped>
.plusContainer {
  max-width: 225px;
  height: 121.6px;
  background-color: #696969;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 50px 102px;
}
</style>
