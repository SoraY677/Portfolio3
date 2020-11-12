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
main {
  width: 100%;
  height: 100%;
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
  overflow-y: auto;
}
</style>