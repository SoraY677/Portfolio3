<template>
 <div class="base-frame">
  <Menu />
  <PageName :name="pageName" />
  <nuxt />
 </div>
</template>

<script>
import PageName from "@/components/PageName";
import Menu from "~/layouts/LMenu.vue";
export default {
 data() {
  return {
   pageName: "",
  };
 },
 components: {
  Menu,
  PageName,
 },
 mounted() {
  this.pageName = this.$route.name;
 },
};
</script>