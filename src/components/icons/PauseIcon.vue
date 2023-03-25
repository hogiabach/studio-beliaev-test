<template>
  <svg
    @click="handleClick"
    class="icon"
    width="10"
    height="20"
    viewBox="0 0 10 20"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <rect x="7" width="3" height="20" fill="white" />
    <rect width="3" height="20" :fill="color" />
  </svg>
</template>

<script>
export default {
  props: {
    handleClick: {
      type: Function,
      required: true
    },
    color: {
      type: String,
      required: true
    }
  }
}
</script>

<style>
.icon:hover {
  cursor: pointer;
}
</style>
