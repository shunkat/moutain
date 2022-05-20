<template>
  <div id="app">
    <v-app id="inspire">
      <v-container >
        <!-- ページ名 -->
        <p class="text-h5 font-weight-bold mb-8">{{ content.name }}さんの紹介ページ</p>
        <v-row>
          <!--写真5枚のグリッド-->
          <v-row class="d-flex justify-space-between" no-gutters>
            <v-col cols="3">
              <v-img class="clipping rounded-l-lg" :src="content.image.url" height="80vh" />
            </v-col>
            <v-col cols="3" class="pr-3 pl-3">
              <v-row no-gutters>
                <v-img class="clipping" :src="content.image.url" height="40vh"/> 
              </v-row>
              <v-row no-gutters >
                <v-img class="clipping" :src="content.image.url" height="40vh" /> 
              </v-row>
            </v-col >
            <v-col cols="3" class="pr-3">
              <v-img class="clipping" :src="content.image.url" height="80vh"/> 
            </v-col>
            <v-col cols="3">
              <v-img class="clipping rounded-r-lg" :src="content.image.url" height="80vh"/> 
            </v-col>
          </v-row>
              
          <v-col cols="8">
            <v-col cols="12" align="left">
                <v-spacer class="my-16" />
                <v-row>
                  <v-col cols="12" align="left" >
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
                    <p class="text-h7">関東周辺</p>
                  <!--TODO:コンテンツの埋め込み-->
                  </v-row>
                  <!-- 得意分野 -->
                  <v-row>
                      <p class="h7  pl-3 mt-3">得意分野</p>
                    <v-col  v-for="genre in content.genres" :key="genre.id">
                      <p class="text-h7 text-center" >{{ genre }}</p>
                    </v-col>
                  </v-row>
            <!-- 所持している資格 -->
            <v-col>
            <v-row>
              <p class="text-h7 mr-10">所持している資格</p>
              <p class="text-h7  mb-12">クライミング(特にマルチピッチ)・雪山</p>
              <!--TODO:コンテンツの埋め込み-->
            </v-row>
            </v-col>
            <v-divider></v-divider>
            </v-col>
            <!-- レンタル品一覧 -->
            <v-col>
              <p class="font-weight-bold">レンタル品一覧</p>
              <p class="font-weight-bold mb-12">ピッケル ヘルメット シュラフ アイゼン マット ビーコン 確保器 カラビナ スリング ハーネス 登山靴 ハイドレーション スノーシュー クライミングシューズ</p>
              <!--TODO:コンテンツの埋め込み-->
              <v-divider></v-divider>
            </v-col>
            <!--ガイドさんへの質問コーナー-->
            <v-col>
              <p class="font-weight-bold">ガイドさんへの質問コーナー</p>
              <p class="text-h7  mb-12">Q1.一番登っている山はどこですか？</p>
              <v-row>
                <v-img class="ml-4 mt-7"  contain max-height="40" max-width="40" :src="content.image.url" />
              <v-col cols="10">
                <div class="my-parts-content">最も好きな山は妙義山です。 生まれて初めて岩場に挑戦した山で、最も登っている山でもあります。 頂上からの景色がとても素敵です。 ツアーに参加されたお客様からの評価も高く、お勧めの一山です。 是非一緒に挑戦しましょう。
                </div>
              </v-col>
              </v-row>
              <!--TODO:コンテンツの埋め込み-->
              <v-divider></v-divider>
            </v-col>
            <!-- アピールメッセージ -->
              <v-col>
                <p class="font-weight-bold">アピールメッセージ</p>
                <p class="text-h7  mb-12">得意なことは、食べられる野草を使って調理をしたり、スペシャルドリンクを考えたりする ことです。 野草料理を召し上がった人に、美味しいと思ってもらえるよう、いつも工夫とリサーチをし ています。 地域に伝わる野草の言い伝えも紹介しています。料理を交えてお話しができれば幸いです。</p>
                <!--TODO:コンテンツの埋め込み-->
              </v-col>
          </v-col>
          <!-- 予約機能部分 -->
          <v-col cols="4">
            
            <v-sheet rounded="xl" class="sticky" elevation="5" color="#FFFFFF">
              <p class="request-cost text-h5 ml-11 pt-8">依頼費用の目安<span>￥5,300</span>から</p>
              <!--TODO:コンテンツの埋め込み-->
              <div >
                <v-list rounded="xl" color="##FFFFFF">
                  <v-list-item
                    v-for="n in 2"
                    :key="n"
                    link
                    >
                    <v-list-item-content>
                      <v-list-item-title>
                        <p class="text-h5 font-weight-bold ml-8 mb-6">高尾山ツアー</p> 
                        <v-row>
                          <p class="text-h7 ml-11  ">所要時間</p>
                          <p class="text-h7  ml-12 ">120分</p>
                        <!--TODO:コンテンツの埋め込み-->
                        </v-row>
                        
                        <v-row>
                          <p class="text-h7 ml-11  ">難易度</p>
                          <p class="text-h7  ml-16 mb-12">中級</p>
                        <!--TODO:コンテンツの埋め込み-->
                        </v-row>
                      </v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
                  <v-list-item
                    link
                    color="#000000"
                    align="center"
                  >
                    <v-list-item-content
                    >
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
.clipping{
width:100%;
height:100%;
object-fit:cover;
}

.request-cost span {
  color:#D13A3A;
}

.my-parts-content {
  position: relative;
  display: inline-block;
  margin: 0 0 1.5em 15px;
  padding: 9px 12px;
  min-width: 120px;
  max-width: 100%;
  color: #555;
  font-size: 16px;
  background: #FFF;
  border: solid 1px #555;
  border-radius: 8px;
  box-sizing: border-box;
}

.my-parts-content::before {
  content: "";
  position: absolute;
  top: 30%;
  left: -23px;
  margin-top: -12px;
  border: 12px solid transparent;
  border-right: 11px solid #FFF;
  z-index: 2;
}

.my-parts-content::after {
  content: "";
  position: absolute;
  top: 30%;
  left: -29px;
  margin-top: -14px;
  border: 14px solid transparent;
  border-right: 15px solid #555;
  z-index: 1;
}

.my-parts-content p {
  margin: 0;
  padding: 0;
}

.overflow-hidden{
  overflow: hidden;
}

/* TODO:↑これいらないかも */

.sticky {
    position: sticky;
    top: 70px;
}
</style>
