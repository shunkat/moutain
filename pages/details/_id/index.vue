<template>
  <v-row justify="center" align-content="center" class="mx-16">
    <v-col cols="12" align="center">
      <v-spacer class="my-16" />

      <v-row>
        <v-col cols="6" align="right">
          <v-img contain height="300" :src="content.image.url" />
        </v-col>
        <v-col cols="6" align="left" class="my-8">
          <p class="text-h3 mb-8">{{ content.name }}</p>
          <p class="text-h6 text--primary">{{ content.about }}</p>
        </v-col>
      </v-row>

      <v-spacer class="my-16" />

      <!-- 個人のホームページへのリンク -->
      <p class="text-h5">連絡先</p>
      <p class="text-h6 text--secondary mb-12">{{ content.connect }}</p>

      <!-- 使用技術 -->
      <p class="text-h5">年齢</p>
      <p class="text-h6 text--secondary mb-12">{{ content.age }}</p>

      <!-- 果たした役割 -->
      <p class="text-h5">性別</p>
      <p class="text-h6 text--secondary mb-12">{{ content.sex[0] }}</p>

      <!-- 得意領域 -->
      <p class="text-h5">得意領域</p>
      <v-row>
        <v-col v-for="genre in content.genres" :key="genre.id">
        <p class="text-h6 text--secondary mb-12">{{ genre }}</p>
        </v-col>
        <!-- 得意領域の詳細な説明 -->
        <p class="text-h6 text--secondary mb-12">{{ content.genreDetail }}</p>
      </v-row>



    </v-col>

    <p class="button-area">
      <nuxt-link to="/">back</nuxt-link>
    </p>
  </v-row>
</template>

<script>
export default {
  async asyncData({ $microcms, params }) {
    const content = await $microcms.get({
      endpoint: `guides/${params.id}`,
    });
    return {
      content,
    };
  },
};
</script>
