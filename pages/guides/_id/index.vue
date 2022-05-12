<template>
  <div id="app">
    <v-app id="inspire">
      <v-container>
        <!-- ページ名 -->
        <p class="text-h5 font-weight-bold mb-8">{{ content.name }}さんの紹介ページ</p>
        <v-row>
          <!--写真5枚のグリッド-->
          <v-container class="white">
                  <v-row>
                    <v-col cols="3" >
                     <v-img  :src="content.image.url" />
                    </v-col>
                    <v-col cols="2" >
                      <v-row no-gutters>
                        <v-img   :src="content.image.url" /> 
                      </v-row>
                      <v-row no-gutters>
                        <v-img   :src="content.image.url" /> 
                      </v-row>
                    </v-col >
                    <v-col cols="3">
                      <v-img  :src="content.image.url" /> 
                    </v-col>
                    <v-col cols="3">  
                      <v-img :src="content.image.url" /> 
                    </v-col>
                  </v-row>
              </v-container>
              
          <v-col cols="8">
            <v-col cols="12" align="left">
                <v-spacer class="my-16" />
                <v-row>
                  <!--幅.？.？-->
                  <v-col cols="12" align="left" class="mb-0">
                      <v-row>
                        <!-- アイコン画像と画像サイズ -->
                        <v-img class="ml-4"  contain max-height="40" max-width="40" :src="content.image.url" />
                        <!-- 名前と年齢-->
                        <p class="text-h5 font-weight-bold">{{ content.name }}さん</p>
                        <p class="text-h7  ml-4 mr-2 mt-2">{{ content.age }}歳</p>
                        <!-- 性別 -->
                        <p class="text-h7  mb-12 mt-2">{{ content.sex[0] }}性</p>
                      </v-row>         
                      <v-col> 
                        <!-- プロフィール -->      
                        <p class="text-h6 text--primary">{{ content.about }}</p>
                      </v-col>
                  </v-col>
                </v-row>

                <v-spacer class="my-16" />
                  <!--活動エリア -->
                  <v-row>
                    <p class="h7 ml-3 mr-10">活動エリア</p>
                    <p class="text-h7">{{ content.age }}</p>
                  </v-row>
                  <!-- 得意分野 -->
                  <v-row>
                    <v-col>
                      <p class="h7 ">得意分野</p>
                    </v-col>
                    <v-col v-for="genre in content.genres" :key="genre.id">
                      <p class="text-h7  ">{{ genre }}</p>
                    </v-col>
                  </v-row>
              
              <!-- 得意分野の詳細な説明 -->
              <v-col>
                <p class="text-h7 mb-12">{{ content.genreDetail }}</p>
              </v-col>
            </v-col>
            <!-- 資格 -->
            <v-col>
              <p class="text-h7">所持している資格</p>
              <p class="text-h7  mb-12">{{ content.sex[0] }}</p>
              <v-divider></v-divider>
            </v-col>
            <!-- レンタル品一覧 -->
            <v-col>
              <p class="font-weight-bold">レンタル品一覧</p>
              <p class="font-weight-bold mb-12">{{ content.sex[0] }}</p>
              <v-divider></v-divider>
            </v-col>
            <!--ガイドさんへの質問コーナー-->
            <v-col>
              <p class="font-weight-bold">ガイドさんへの質問コーナー</p>
              <p class="text-h7  mb-12">{{ content.sex[0] }}</p>
              <v-divider></v-divider>
            </v-col>
            <!-- アピールメッセージ -->
            
              <v-col>
                <p class="font-weight-bold">アピールメッセージ</p>
                <p class="text-h7  mb-12">{{ content.sex[0] }}</p>
              </v-col>
            
          </v-col>

          <!-- 予約機能部分 -->
          <v-col cols="4">
            
            <v-sheet rounded="xl" class="sticky" elevation="5" color="#FFFFFF">
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
                    align="center"
                  >
                    <v-list-item-content>
                  <v-col>   
                    <v-btn
                    width="200"
                    align="center"
                    color="#37D45A">
                    <p class="white--text mt-4">メッセージを送る</p>   
                    </v-btn>
                  </v-col>
                  </v-list-item-content>
                  </v-list-item>
                </v-list>
              </div>
            </v-sheet>
          </v-col>
        </v-row>
      </v-container>
    </v-app>
  </div>
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
    top: 70px;
}
</style>
