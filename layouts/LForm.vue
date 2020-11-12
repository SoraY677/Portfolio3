<template>
 <div class="base-frame">
  <Menu />
  <nuxt />
 </div>
</template>

<script>
import Menu from "~/layouts/LMenu.vue";
export default {
 components: {
  Menu,
 },
};
</script>