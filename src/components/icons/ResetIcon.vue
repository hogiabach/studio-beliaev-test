<template>
  <svg
    @click="handleClick"
    class="icon"
    width="20"
    height="20"
    viewBox="0 0 20 20"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <rect width="20" height="20" :fill="color" />
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
