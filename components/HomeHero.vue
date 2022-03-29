<template>
  <section class="home-hero">
    <v-container  mt-0 pt-0 fluid fill-height class="home-hero__content"
      >
      <v-row>
        <v-col 
          class="home-hero__content-text"
          >
          <p>Welcome to Santanzin.</p>  
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>

<style  lang="scss" scoped>
  // .v-container {
  //   margin:0px
  // }

  .home-hero__content {
    background: url("../assets/img/home-img.jpg");
    background-size: cover;
    background-position: center center;
    width: 100%;
    height: 90vh;
    text-align:"center";
  
    // /* ここから追加 */
    // @include display_pc {
    //   height: 100vh;
    // }
    /* ここまで追加 */
  
    &-text {
      color: white;
      text-align: center;
      font-size: 28px;
      font-weight: bold;
  
      // /* ここから追加 */
      // @include display_pc {
      //   font-size: 40px;
      // }
      /* ここまで追加 */
    }
  }
</style>