<template>


<v-col cols="4" class="px-12">

  <v-for="content in contents.contents" :key="content.id">
  <nuxt-link :to="`/details/${content.id}/`">
    <v-card elevation="2" height="200">
      <v-card-title>{{ content.name }}</v-card-title>
      <v-img :src="content.image.url" height="240" />
    </v-card>
  </nuxt-link>

    <div class="button-area">
      <nuxt-link to="/contact/" class="button">お問い合わせ</nuxt-link>
    </div>
</v-col>

</template>

<script>
export default {
  async asyncData({ $microcms }) {
    const contents = await $microcms.get({
      endpoint: "guides",
    });
    return {
      contents,
    };
  },
};
</script>
