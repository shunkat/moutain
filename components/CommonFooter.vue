<template>
  <footer>
    <v-footer
      dark
      padless
    >
      <v-card
        flat
        tile
        width="100vw"
        class="#BBBBBB lighten-1 white--text text-center"
      >
        <v-card-text>
          <v-btn
            v-for="icon in icons"
            :key="icon"
            class="mx-4 white--text"
            icon
          >
            <v-icon size="24px">
              {{ icon }}
            </v-icon>
          </v-btn>
        </v-card-text>

        <v-card-text class="white--text pt-0">
          このサイトは、あなたに最適な山岳ガイドを探してくれます。また、トラブルを避けるため予約する際に、当日の持ち物や費用、注意事項を記載しているのでご一読下さい。
        </v-card-text>
        <v-card-text class="white--text pt-0">
          This site will help you find the best mountain guide for you. Please also read the information on what to bring, costs, and precautions to take on the day of the tour when booking to avoid problems.
        </v-card-text>

        <v-divider></v-divider>

        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} — <strong>Santanzin</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </footer>
</template>
<script>
  export default {
    data () {
      return {
        icons: [
          'mdi-facebook',
          'mdi-twitter',
          'mdi-linkedin',
          'mdi-instagram',
        ],
      }
    }
  }
</script>
<style lang="scss" scoped>
    
</style>