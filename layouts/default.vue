<template>
    <v-app v-cloak>
　　　<!-- ヘッダー（app:コンテンツの幅を自動調整＆固定） -->
      <v-app-bar
      app
      color="indigo"
      style="color: white"
      >
        <v-app-bar-nav-icon　color="white" @click="drawer = true"></v-app-bar-nav-icon>
        <v-toolbar-title>
          TAKTAK's Portfolio
        </v-toolbar-title>
        <v-spacer />
      </v-app-bar>
      <!-- ヘッダー終わり -->

      <!-- ナビゲーションメニュー（drawer（変数）:メニュー表示・非表示を制御） -->
      <v-navigation-drawer
         v-model="drawer"
         fixed
         temporary
       >
         <!-- メニューのリスト化 -->
         <v-list
           nav
           dense
         >
           <!-- リストのグループ化 -->
           <v-list-item-group
             v-model="group"
             active-class="indigo--text text--accent-4"
           >
            <!-- アイコン＆文字列：クリック遷移設定（それぞれのコンポーネントへページ内遷移） -->
            <nuxt-link v-scroll-to="'#profile'" to>
             <v-list-item>
               <v-list-item-icon>
                 <!-- mdi-XXX:アイコンを指定できる(material design iconで検索！) -->
                 <v-icon>mdi-account</v-icon>
               </v-list-item-icon>
               <v-list-item-title>
                   profile
               </v-list-item-title>
             </v-list-item>
            </nuxt-link>
　　　　　　　<!-- vue-scrollto.jsの使用（v-scroll-to, ページ内のid(history)に遷移 -->
            <nuxt-link v-scroll-to="'#history'" to>
             <v-list-item>
               <v-list-item-icon>
                 <v-icon>mdi-history</v-icon>
               </v-list-item-icon>
               <v-list-item-title>
                   history
               </v-list-item-title>
             </v-list-item>
            </nuxt-link>
            <nuxt-link v-scroll-to="'#work'" to>
             <v-list-item>
               <v-list-item-icon>
                 <v-icon>mdi-folder</v-icon>
               </v-list-item-icon>
               <v-list-item-title>
                   work
               </v-list-item-title>
             </v-list-item>
            </nuxt-link>
            <nuxt-link v-scroll-to="'#contact'" to>
             <v-list-item>
               <v-list-item-icon>
                 <v-icon>mdi-email</v-icon>
               </v-list-item-icon>
               <v-list-item-title>
                   contact
               </v-list-item-title>
             </v-list-item>
             </nuxt-link>
           </v-list-item-group>
         </v-list>
       </v-navigation-drawer>
      <!-- ナビゲーションメニュー終わり -->

      <!-- ページ埋め込み（pages/*.vueの内容が埋め込まれる） -->
      <v-content
      fluid>
          <nuxt />
      </v-content>

      <!-- フッター（app:コンテンツの幅を自動調整＆固定） -->
      <v-footer
      app
      color="indigo"
      >
      <v-spacer />
      <span style="color: white">&copy; 2020 Takahashi Takuya. All Rights Reserved.</span>
      </v-footer>
      <!-- フッター終わり -->
    </v-app>
</template>

<script>
export default {
  data () {
    return {
          drawer: false,
          group: null,
    }
  }
}
</script>
<style>
/* コンパイルされていない変数を隠す設定 */
[v-cloak] {
  display: none;
}
/* リストのレイアウト、色修正 */
.v-application a {
    color: black;
    text-decoration: none;
}
/* ボタンのホバー設定 */ 
.theme--light.v-btn:hover::before {
    opacity: 0.2;
}
</style>