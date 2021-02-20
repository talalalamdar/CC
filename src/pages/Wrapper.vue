<template>
  <div class="wrapper">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'Wrapper',
}
</script>

<style scoped>
  .wrapper {
    width: 100%;
    height: 100%;
    max-width: 1024px;
    margin: 0 auto;
  }
</style>
