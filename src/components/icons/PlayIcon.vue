<template>
  <svg
    @click="handleClick"
    class="icon"
    width="17"
    height="20"
    viewBox="0 0 17 20"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <path d="M0 20V0L17 10L0 20Z" :fill="color" />
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
