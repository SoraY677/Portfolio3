<template>
  <section>
    <h1>{{ item.title }}</h1>
    <div>
      <p v-for="sen in item.sentence" :key="sen.id">{{ sen }}</p>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    item: {},
  },
};
</script>

<style scoped>
</style>