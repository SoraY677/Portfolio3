<template>
 <div class="l-square">
  <div class="l-square-content">
   <button @click="$emit('click')">
    <div class="bar-container">
     <span class="bar"></span>
    </div>
   </button>
  </div>
 </div>
</template>

<style scoped>
button {
 width: 100%;
 height: 100%;
 padding: 15%;
 border-radius: 50%;
}

.bar-container {
 position: relative;
 width: 100%;
 height: 100%;
}

.bar,
.bar::before {
 position: absolute;
 top: 50%;
 left: 0;
 width: 100%;
 background-color: #2e2e2e;
}
.bar {
 transform: translateY(-50%);
 height: 10%;
}

.bar::before {
 content: "";
 height: 100%;
 transform: translateY(-50%) rotate(90deg);
}
</style>