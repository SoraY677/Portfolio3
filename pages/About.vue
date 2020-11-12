<template>
  <div>
    <MainIntro class="pb-2" />
    <ul>
      <li class="pb-1" v-for="item in ability" :key="item.id">
        <Ability :item="item" />
      </li>
    </ul>
  </div>
</template>

<script>
import MainIntro from "@/components/About/MainIntro";
import Ability from "@/components/About/AbilityCard";
export default {
  layout: "LForm",
  components: {
    MainIntro,
    Ability,
  },
  data() {
    return {
      ability: [
        {
          title: "資格",
          sentence: ["・基本情報技術者", "・応用情報技術者"],
        },
        {
          title: "所属",
          sentence: [
            "・学生団体連合会(引退)/元会計",
            "・創作サークル(デジタルコンテンツ研究会)/プログラミング班長",
            "・大谷研究室/ゼミ長",
          ],
        },
        {
          title: "技術系",
          sentence: [
            "・フロントエンド:Vue/React勉強中",
            "・機械学習・AI:進化計算アルゴリズム/ニューラルネット系",
            "・バックエンド:Flask/PHP",
            "・自動化ツールなど:python",
          ],
        },
        {
          title: "アルバイト",
          sentence: [
            "・飲食店/半年と2年",
            "・設営/数か月",
            "・大学の学生アシスタント",
            "・友人の会社のフロントエンド",
          ],
        },
      ],
    };
  },
};
</script>

<style scoped>
</style>