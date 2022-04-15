<template>
  <header>
    <v-app-bar
      app
      dark
      dense
      color="teal darken-3"
    >
      <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>
      <!-- Page Titile -->
      <v-avatar>
        <img
          src="../assets/img/square-logo.png"
          alt="探そう山のガイドさん"
          width="24px"
        >
      </v-avatar>
      <v-toolbar-title>探そう山のガイドさん</v-toolbar-title>
      <!-- <v-container
      > -->
      <v-tabs
        centered
      >
        <v-tab

          v-for="(menuItem, index) in menuItems"
          :key="index"
        >
          {{ menuItem.name }}
        </v-tab>
      </v-tabs>
    </v-app-bar>
    <!-- ハンバーガーメニュー -->
    <v-navigation-drawer
      v-model="drawer"
      fixed
      temporary
    >
      <v-list
        nav
        dense
      >
        <v-list-item-group>
          <v-list-item
            v-for="(menuItem, index) in menuItems"
            :key="index"
          >
            <v-list-item-title>{{ menuItem.name }}</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </header>

</template>

<script>
  import constants from '../src/style/common/header_item.js'

  export default {
    data () {
      return {
        drawer: false,
        menuItems: constants.menuItems
      }
    }
  }
</script>
<style lang="scss" scoped>
@import 'src/style/common/_mixin.scss';

.v-toolbar__title {
  overflow: visible !important;
  margin-right: 50px !important;
}
.v-app-bar__nav-icon {
  @include display_pc {
    display: none !important;
  }
}
.v-tabs {
  display: none;

  @include display_pc {
    display: block !important;
  }
}
</style>
