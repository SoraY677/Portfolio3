<template>
  <p class="container">
    {{ name }}
  </p>
</template>

<script>
export default {
  props: {
    name: "",
  },
};
</script>

<style scoped>
.container {
  position: absolute;
  left: 0;
  bottom: 10px;
  font-size: 6rem;
  opacity: 0.6;
  writing-mode: vertical-rl;
}
</style>