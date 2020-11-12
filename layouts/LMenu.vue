<template>
 <nav :class="{ active: isActive }">
  <Menu
   @click="isActive = !isActive"
   class="menu-btn"
   :class="{ active: isActive }"
  />
  <ul>
   <li
    v-for="item in linkList"
    :key="item.id"
    class="menu-item"
    :class="{ active: isActive }"
   >
    <nuxt-link :to="item">
     {{ item }}
    </nuxt-link>
   </li>
  </ul>
 </nav>
</template>

<script>
import Menu from "~/components/Menu.vue";
export default {
 data() {
  return {
   isActive: false,
   linkList: ["About", "Work", "Blog", "Contact"],
  };
 },
 components: {
  Menu,
 },
};
</script>

<style scoped>
nav {
 position: fixed;
 left: 10px;
 width: 50px;
 height: 100%;
 transform: translateY(10px);
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

.menu-item {
 opacity: 0;
 transition-delay: 0s;
 transition-duration: 0s;
}

.menu-item.active {
 opacity: 1;
 transition-delay: 0.5s;
 transition-duration: 0.5s;
}
</style>