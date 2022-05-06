<template>
  <v-container>
    <v-row>
      <v-col cols="8">
        <!-- 自己紹介部分 -->
        <p class="text-h5 font-weight-bold mb-8">{{ content.name }}さんの紹介ページ</p>
        <v-col cols="12" align="left">
          <!-- プロフィール画像6枚 -->
          <!--写真5枚のグリッド-->
         <div id="app">
  <v-app id="inspire">
    <v-container class="grey lighten-5">
      <v-col>
        <v-row>
          <v-card>
            <v-img contain height="100" :src="content.image.url" />
          </v-card>
          <v-col no-gutters>
            <v-row
              cols="8"
            >
              <v-card
                class="pa-2"
                outlined
                style="background-color: lightgrey;"
                tile
              >
                Level 2: .col-8 .col-sm-6
              </v-card>
            </v-row>
            <v-row
              cols="8"
              sm="6"
            >
              <v-card
                class="pa-2"
                outlined
                style="background-color: lightgrey;"
                tile
              >
                Level 3: .col-8 .col-sm-6
              </v-card>
            </v-row>
          </v-col>
        </v-row>
      </v-col>
    </v-container>
  </v-app>
</div>
      
a

          <v-spacer class="my-16" />
          <v-row>
            <!--幅.？.？-->
            <v-col cols="50" align="left" class="mb-0">
            
              <v-row>
              <!-- アイコン画像と画像サイズ -->
              <v-img contain height="56" :src="content.image.url" />

              <!-- 名前と年齢-->
              <p class="text-h5 font-weight-bold">{{ content.name }}さん</p>
              <p class="text-h7  ml-4 mr-2 mt-2">{{ content.age }}歳</p>

            <!-- 性別 -->
          <p class="text-h7  mb-12 mt-2">{{ content.sex[0] }}性</p>
              <p class="text-h6 text--primary">{{ content.about }}</p>
              </v-row>
            </v-col>
           </v-row>

          <v-spacer class="my-16" />

          <!--活動エリア -->
          <v-row>
          <p class="h7 mr-10">活動エリア</p>
          <p class="text-h7">{{ content.age }}</p>
          </v-row>

         
          <!-- 得意分野 -->
          <v-row>
            <v-col>
              <p  class="h7 ">得意分野</p>
            </v-col>
            
            <v-col v-for="genre in content.genres" :key="genre.id">
              <p class="text-h7 ml-10 ">{{ genre }}</p>
            </v-col>
            <!-- 得意分野の詳細な説明 -->
            <v-col>
              <p class="text-h7 mb-12">{{ content.genreDetail }}</p>
            </v-col>
          </v-row>
          </v-col>

          <!-- 資格 -->
          <p class="text-h7">所持している資格</p>
          <p class="text-h7  mb-12">{{ content.sex[0] }}</p>
<v-divider></v-divider>
          <!-- レンタル品一覧 -->
          <p class="font-weight-bold">レンタル品一覧</p>
          <p class="font-weight-bold mb-12">{{ content.sex[0] }}</p>
<v-divider></v-divider>

          <!--ガイドさんへの質問コーナー-->
          <p class="font-weight-bold">ガイドさんへの質問コーナー</p>
          <p class="text-h7  mb-12">{{ content.sex[0] }}</p>
<v-divider></v-divider>
          <!-- アピールメッセージ -->
          <p class="font-weight-bold">アピールメッセージ</p>
          <p class="text-h7  mb-12">{{ content.sex[0] }}</p>
      </v-col>

      <!-- 予約機能部分 -->
      <v-col cols="4">
        <v-sheet rounded="lg" class="sticky" elevation="5" shaped="60" color="#FFFFFF">
          <p class="text-h5 ml-11 pt-8">依頼費用の目安{{ content.age }}から</p>
          <div >
            <v-list color="##FFFFFF">
              <v-list-item
                v-for="n in 2"
                :key="n"
                link
              >
                <v-list-item-content>
                  <v-list-item-title>
                  <p class="text-h5 font-weight-bold ml-8 mb-6">{{ content.sex[0] }}ツアー</p> 
                  <v-row>
                  <p class="text-h7 ml-11  ">所要時間</p>
                  <p class="text-h7  ml-12 ">{{ content.age }}分</p>
                  </v-row>
                  
                  <v-row>
                  <p class="text-h7 ml-11  ">難易度</p>
                  <p class="text-h7  ml-16 mb-12">{{ content.sex[0] }}</p>
                  </v-row>
                  </v-list-item-title>
                </v-list-item-content>
              </v-list-item>

            

              <v-list-item
                link
                color="#000000"

              >
                <v-list-item-content>
                <v-btn
                 width="10"
                 color="#37D45A">
                <p class="white--text mt-4">メッセージを送る</p>   
                </v-btn>
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
