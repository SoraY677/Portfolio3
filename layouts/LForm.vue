<template>
  <div class="base-frame">
    <Menu />
    <main>
      <div class="left-side">
        <PageName :name="getPageName" />
      </div>
      <div class="right-side">
        <nuxt />
      </div>
    </main>
    <LFooter />
  </div>
</template>

<script>
import PageName from "@/components/PageName";
import Menu from "~/layouts/LMenu.vue";
import LFooter from "~/layouts/LFooter.vue";
export default {
  data() {
    return {
      pageName: "",
    };
  },
  components: {
    Menu,
    LFooter,
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
main {
  width: 100%;
  min-height: 100%;
  overflow: hidden;
}

.left-side {
  position: fixed;
  width: 20%;
  height: 100%;
}

.right-side {
  float: right;
  width: 80%;
  height: 100%;
  padding: 3%;
}
</style>