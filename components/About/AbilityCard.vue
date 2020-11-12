<template>
  <section class="container">
    <h1>{{ item.title }}</h1>
    <div class="sentence">
      <p v-for="sen in item.sentence" :key="sen.id">
        {{ sen }}
      </p>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    item: {},
    sentence: [],
  },
};
</script>

<style scoped>
.container {
  padding: 1em;
  border: 1px solid rgba(46, 46, 46, 0.65);
  border-radius: 1em;
  box-shadow: 2px 2px 2px #2e2e2e;
}

h1 {
  padding-left: 0.2em;
  border-left: 0.3em solid rgba(46, 46, 46, 0.65);
}

.sentence {
  padding-top: 0.2em;
  padding-left: 1em;
}
</style>