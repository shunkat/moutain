<template>
  <v-app id="inspire">
    <CommonHeader/>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <CommonFooter/>
  </v-app>
</template>

<script>
import CommonHeader from "../components/CommonHeader.vue";
import CommonFooter from "../components/CommonFooter.vue";

export default {
  components: {
    CommonHeader,
    CommonFooter
  },
};
</script>
<style lang="scss" scoped>
// .v-container{
//   width: "100vw";
// }
</style>
