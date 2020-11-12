<template>
  <section>
    <h1 class="name">SoraYAMAGUCHI</h1>
    <div class="sentence">
      <p v-for="item in sentence" :key="item.id">{{ item }}</p>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      sentence: [
        "東京都市大学メディア情報学部情報システム学科第4学年に所属する21歳。",
        "フロントエンドやらバックエンドやらAIやらいろいろできます。",
        "趣味は筋トレとニュース見るのと読書。",
        "今は特に画像処理系に興味あり。",
      ],
    };
  },
};
</script>

<style scoped>
.name {
  position: relative;
  font-size: 2.6em;
}

.sentence {
  padding-top: 1em;
  padding-left: 1em;
}
</style>