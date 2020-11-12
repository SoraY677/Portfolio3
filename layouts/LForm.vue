<template>
 <div class="base-frame">
  <Menu />
  <div class="left-side">
   <PageName :name="getPageName" />
  </div>
  <div class="right-side">
   <nuxt />
  </div>
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

<style scoped>
.left-side,
.right-side {
 float: left;
 height: 100%;
}

.left-side {
 position: relative;
 width: 20%;
}

.right-side {
 width: 80%;
 padding: 3%;
}
</style>