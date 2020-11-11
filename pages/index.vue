<template>
 <section class="keyvisual l-flex-central">
  <div ref="keyvisual_inner" class="keyvisual-inner l-flex-central">
   <div class="title-container">
    <h1>SoraY677</h1>
    <h2>Portfolio</h2>
   </div>
  </div>
 </section>
 <!-- <LMenu /> -->
</template>

<script>
export default {
 layout: "LTop",
 mounted() {
  const pcTrigger = this.$refs["keyvisual_inner"];
  let count = 0;
  pcTrigger.addEventListener("animationend", () => {
   count++;
   if (count == 5) {
    this.$router.push("/About");
   }
  });
 },
};
</script>

<style scope>
.keyvisual {
 width: 100%;
 height: 100%;
 padding: 10%;
}

.keyvisual-inner {
 position: relative;
 display: flex;
 width: 100%;
 height: 100%;
 border: 5px solid #2e2e2e;
 background-color: #2e2e2e;
 color: #fff;
 animation: block-emp 1s ease 0s 1 alternate forwards,
  block-shrink 1.4s ease 2.5s 1 alternate forwards;
}

.keyvisual-inner::before {
 content: "";
 position: absolute;
 top: -5%;
 left: -4%;
 width: 108%;
 height: 110%;
 border: 5px solid #2e2e2e;
 padding: 20px;
}

.title-container {
 padding-left: 2em;
 border-left: 2px solid #fff;
 opacity: 0;
 animation: fade-in 1s ease 1s 1 alternate forwards;
}

h1 {
 opacity: 0;
 font-size: 5rem;
 animation: fade-in 1s ease 1s 1 alternate forwards;
}

h2 {
 opacity: 0;
 font-size: 3rem;
 animation: fade-in 1s ease 1s 1 alternate forwards;
}

@keyframes block-emp {
 0% {
  width: 20%;
  height: 20%;
  opacity: 1;
 }
 100% {
  width: 100%;
  height: 100%;
  opacity: 1;
 }
}

@keyframes block-shrink {
 0% {
  width: 100%;
  height: 100%;
  opacity: 1;
 }
 80% {
  opacity: 1;
 }

 100% {
  width: 0%;
  height: 0%;
  opacity: 0;
  overflow: hidden;
 }
}

@keyframes fade-in {
 0% {
  opacity: 0;
 }
 100% {
  opacity: 1;
 }
}
</style>

