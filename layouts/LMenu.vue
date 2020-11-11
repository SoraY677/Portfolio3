<template>
 <nav :class="{ active: isActive }">
  <Menu
   @click="isActive = !isActive"
   class="menu-btn"
   :class="{ active: isActive }"
  />
 </nav>
</template>

<script>
import Menu from "~/components/Menu.vue";
export default {
 data() {
  return {
   isActive: false,
  };
 },
 components: {
  Menu,
 },
};
</script>

<style scope>
nav {
 position: fixed;
 left:10px;
 width: 50px;
 height: 100%;
 transform:translateY(10px);
}

nav,
.menu-btn {
 transition-duration: 0.5s;
}

nav.active {
 transform: translateY(50%);
}

.menu-btn.active {
 transform: rotate(135deg);
}
</style>