<template>
  <section class="home-hero">
    <v-container  mt-0 pt-0 fluid fill-height class="home-hero__content"
      >
      <v-row class="home-hero__content-text">
        <transition-group tag="div" class="title">
          <span v-for="el in text" :key="el.id" class="item home-hero__content-text" v-text="el.text"/>
        </transition-group>
      </v-row>
    </v-container>
  </section>

</template>
<script>
export default {
  data() {
    return {
      timer: null,
      index: 0,
      // オリジナルメッセージ
      original: [
        '山をもっと、身近に',
        '山をもっと、安全に',
        '山をもっと、楽しく'
      ],
      // 分解したメッセージ
      messages: [],
      text: ''
    }
  },
  watch: {
    autoplay(val) {
      clearTimeout(this.timer)
      if (val) {
        this.ticker()
      }
    }
  },
  created() {
    this.messages = this.original.map(el => this.convText(el))
    this.text = this.messages[0]
    this.ticker()
  },
  methods: {
    // デモ用のオートタイマー
    ticker() {
      this.timer = setTimeout(() => {
          this.index = this.index < this.messages.length-1 ? this.index + 1 : 0
          this.text = this.messages[this.index]
          this.ticker()
      }, 5000)
    },
    // テキストを分解してオブジェクトに
    convText(text) {
      const alms = {}
      const result = text.split('').map(el => {
        alms[el] = alms[el] ? ++alms[el] : 1
        return { id: `${el}_${alms[el]}`, text: el }
      })
      return Object.freeze(result) // 監視しない
    }
  }
}
</script>

<style lang="scss" scoped>
.home-hero__content {
  background: url("../assets/img/home-img.jpg");
  background-size: cover;
  background-position: center center;
  width: 100%;
  height: 90vh;
  text-align:"center";

  &-text {
    color: white;
    text-align: center;
    font-size: 42px;
    font-weight: bold;
  }
}

.item {
  display: inline-block;
  min-width: 0.3em;
}

/* トランジション用スタイル */
.v-enter-active,
.v-leave-active,
.v-move {
  transition: all 1s;
}

.v-leave-active {
  position: absolute;
}

.v-enter,
.v-leave-to {
  opacity: 0;
  transform: translateY(-30px);
}
</style>
