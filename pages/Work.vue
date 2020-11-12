<template>
  <div>
    <workList :list="list" />
  </div>
</template>

<script>
import workList from "@/components/Work/WorkList";
export default {
  layout: "LForm",
  components: {
    workList,
  },
  data() {
    return {
      list: [
        {
          title: "test",
          sentence: ["test"],
        },
        {
          title: "test",
          sentence: ["test"],
        },
        {
          title: "test",
          sentence: ["test"],
        },
        {
          title: "test",
          sentence: ["test"],
        },
      ],
    };
  },
};
</script>

<style scoped>
</style>