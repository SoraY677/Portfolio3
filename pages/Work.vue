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
          title: "ポートフォリオ3",
          sentence: ["制作したポートフォリオその３。"],
        },
        {
          title: "いいねシステム",
          sentence: [
            "YahooHackDay2019にて同研究室の先輩方と一緒に開発した。",
            "当日は企画出しとプロジェクトマネジメントを主としてチームに貢献した。",
            "24時間以内というタイムリミットの中、寝ずに続け何とか完成に持ち込んだ。",
          ],
        },
        {
          title: "大谷研究室 夏の事例研究コンペ",
          sentence: [
            "大谷研究室で夏に行われたものの成果物。",
            "社会問題に対し進化計算アルゴリズムである人工蜂コロニーアルゴリズムを用いて挑戦。",
            "研究生9名の中で群を抜いて優勝。",
          ],
        },
        {
          title: "ティミデート",
          sentence: [
            "友人が起業した会社でのシステム開発にフロントエンドとして参加した際のもの",
            "フロントエンドとしておよそ60ページ程度のサイトに対し、Vueを用いてプロトタイプを製作。",
            "制作期間およそ1月半",
          ],
        },
      ],
    };
  },
};
</script>

<style scoped>
</style>