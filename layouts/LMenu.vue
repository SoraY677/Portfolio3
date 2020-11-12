<template>
 <div>
  <div class="overlay" :class="{ active: isActive }"></div>
  <nav :class="{ active: isActive }">
   <div class="menu-btn-container">
    <Menu
     @click="isActive = !isActive"
     class="menu-btn"
     :class="{ active: isActive }"
    />
   </div>
   <ul class="menu-list">
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
 </div>
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
.overlay {
 position: fixed;
 z-index: 99;
 width: 100%;
 height: 100%;
 transform: translateX(-100%);
 transition: 0.2s;
 background-color: #222;
}

.overlay.active {
 transform: translateX(0);
}

nav {
 position: fixed;
 display: flex;
 z-index: 100;
 left: 10px;
 transform: translateY(10px);
}

.menu-btn-container {
 width: 50px;
}

nav,
.menu-btn {
 transition-duration: 0.5s;
}

nav.active {
 transform: translateY(50vh);
}

.menu-btn.active {
 transform: rotate(135deg);
}

.menu-list {
 color: white;
 font-size: 3rem;
 padding-left: 20px;
 transform: translateY(-25%);
}

.menu-item {
 width: 0%;
 overflow: hidden;
 transition-delay: 0s;
 transition-duration: 0s;
}

.menu-item.active {
 width: 100%;
 transition-delay: 0.5s;
 transition-duration: 0.5s;
}

.menu-item > a {
 color: white;
}
</style>