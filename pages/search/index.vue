<template>
<v-col cols="4" class="px-12">
  <v-col v-for="content in guides.contents" :key="content.id">
    <nuxt-link :to="`/details/${content.id}/`">
      <v-card elevation="2" height="200">
        <v-card-title>{{ content.name }}</v-card-title>
        <v-img :src="content.image.url" height="240" />
      </v-card>
    </nuxt-link>
  </v-col>
  <SearchForm></SearchForm>
</v-col>
</template>

<script>
import SearchForm from "../../components/SearchForm.vue"
export default {
  async asyncData({ $microcms }) {
    const guides = await $microcms.get({
      endpoint: "guides",
      // queries: {filters: 'name[contains]'},
    });
    console.log(guides);
    return {
      guides,
    };
  },
  components: {
    SearchForm,
  },
};
</script>
