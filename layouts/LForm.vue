<template>
 <div class="base-frame">
  <Menu />
  <PageName :name="getPageName" />
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
 computed: {
  getPageName: function () {
   return this.$route.name;
  },
 },
};
</script>