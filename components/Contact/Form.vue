<template>
  <form>
    <section class="pb-1">
      <h1>お名前</h1>
      <input
        class="input-area"
        type="text"
        placeholder="山田そら"
        v-model="name"
      />
    </section>

    <section class="pb-1">
      <h1>メールアドレス</h1>
      <input
        class="input-area"
        type="text"
        v-model="mailadress"
        placeholder="example@emial.com"
      />
    </section>

    <section class="pb-2">
      <h1>内容</h1>
      <textarea
        class="content input-area"
        v-model="content"
        placeholder="内容がないようです。"
      ></textarea>
    </section>

    <div>
      <button @click="confirmSend()" type="button">送信</button>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      mailadress: "",
      content: "",
    };
  },
  methods: {
    /**
     * googleformの機能を活用して、メッセージを記録
     */
    async sendMessage() {
      // CORSエラー対策
      const CORS_PROXY = "https://cors-anywhere.herokuapp.com/";
      // Googleフォームのaction属性値
      const GOOGLE_FORM_ACTION =
        "https://docs.google.com/forms/u/0/d/e/1FAIpQLScNaX1t1grG6uIi5qG2pfnpFBf0fGr4S5HtUFESlPiu1xw1Yw/formResponse";
      const params = new FormData();
      params.append("entry.2145197953", this.name);
      params.append("entry.663343677", this.mailadress);
      params.append("entry.1396251703", this.content);
      await this.$axios.$post(CORS_PROXY + GOOGLE_FORM_ACTION, params);
      alert("送信しました。ありがとうございます！");
    },
    /**
     * 送信時に入力不足が存在するかをフィルター
     */
    filterContent() {
      if (this.name == "") return 1; // 名前不足
      if (
        this.mailadress.match(/^[A-Za-z0-9]+[\w-]+@[\w\.-]+\.\w{2,}$/) == null
      )
        return 2; //メールアドレス不足
      if (this.content == "") return 3; // 内容不足

      return 0; //正常
    },

    /**
     * 送信確認
     */
    async confirmSend() {
      const filter = this.filterContent();
      console.log(filter);
      switch (filter) {
        case 0:
          const isSend = window.confirm("送信します。よろしいですか？");
          if (isSend) {
            await this.sendMessage();
          }
          break;
        case 1:
          alert("名前を入力してください");
          break;
        case 2:
          alert("メールアドレスが正しいか確認してください");
          break;
        case 3:
          alert("内容が無いよう！");
          break;
      }
    },
  },
};
</script>

<style scoped>
h1 {
  margin-bottom: 0.3em;
  font-size: 1.2em;
  font-weight: normal;
}

.input-area {
  font-size: 1.3em;
  width: 100%;
  padding: 0.4em;
  border: 1px solid rgba(46, 46, 46, 0.65);
  border-radius: 0.2em;
}

.input-area:focus {
  border: 2px solid #2e2e2e;
  outline: none;
}

.content {
  height: 10em;
}

button {
  width: 100%;
  padding: 0.5em;
  border-radius: 0.6em;
  font-size: 1.2em;
  color: #fff;
  background-color: #2e2e2e;
}
</style>