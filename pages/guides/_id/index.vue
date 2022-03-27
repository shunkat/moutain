<template>
  <v-container>
    <v-row>
      <v-col cols="8">
        <!-- 自己紹介部分 -->
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
      </v-col>

      <!-- 予約機能部分 -->
      <v-col cols="4">
        <v-sheet rounded="lg" class="sticky" color="light-green">
          <p class="text-h6 text--primary ml-8 pt-8">取り扱っているツアー</p>
          <div >
            <v-list color="transparent">
              <v-list-item
                v-for="n in 5"
                :key="n"
                link
              >
                <v-list-item-content>
                  <v-list-item-title>
                    List Item {{ n }}
                  </v-list-item-title>
                </v-list-item-content>
              </v-list-item>

              <v-divider class="my-2"></v-divider>

              <v-list-item
                link
                color="grey lighten-4"
              >
                <v-list-item-content>
                  <v-list-item-title>
                    連絡する
                  </v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-list>
          </div>

        </v-sheet>
      </v-col>
    </v-row>
  </v-container>
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

<style scoped>
.sticky {
    position: sticky;
    top: 120px;
}
</style>
