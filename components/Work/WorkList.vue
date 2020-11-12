<template>
  <ul>
    <li v-for="item in list" :key="item.id"><workItem :item="item" /></li>
  </ul>
</template>

<script>
import workItem from "@/components/Work/WorkItem";
export default {
  props: {
    list: [],
  },
  components: {
    workItem,
  },
};
</script>

<style scoped>
li {
  height: 30vh;
  overflow-x: scroll;
}
</style>