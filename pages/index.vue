<template>
  <section class="home">
    <HomeHero></HomeHero>
    <GuidesList></GuidesList>
  </section>
</template>
<script>
import HomeHero from "~/components/HomeHero.vue";
import GuidesList from "~/components/GuidesList.vue";

export default {
  components: {
    HomeHero,
    GuidesList,
  },
};
</script>
<style lang="scss" scoped>
.home {
  padding-bottom: 50px;
}
</style>
