<template>
  <section class="home">
    <HomeHero></HomeHero>
  </section>
  <!-- <div>
    <nuxt-link to="/guides/">
      <p>フロントページ自由にいじってね</p>
    </nuxt-link>
  </div> -->
</template>
<script>
import HomeHero from "../components/HomeHero.vue";

export default {
  components: {
    HomeHero,
  },
};
</script>
<style lang="scss" scoped>
.home {
  padding-bottom: 50px;
}
</style>
