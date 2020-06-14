<template>
    <div id="work">
            <v-container
            fluid>
                <v-card
                width="100vw"
                >
                <v-card-title
                class="justify-center display-1 font-italic"
                >
                    Work
                </v-card-title>
                <v-row
                >
　　　　            <!-- レスポンシブでバナーサイズ調整(cols:スマホサイズ,sm:タブレットサイズ,md:ラップトップサイズ、maxは12) -->
                    <v-col
                      v-for="(card, index) in cards"
                      :key="card.index"
                      :cols="card.flex.cols"
                      :sm="card.flex.sm"
                      :md="card.flex.md"
                      class="pa-10"
                    >
　　　　　　　　　　　　<!-- リンク設定 -->
                    <a :href="card.redirect_url">
　　　　　　　　　　　　<!-- ホバー設定 -->
                      <v-hover
                        v-slot:default="{ hover }"
                      >
　　　　　　　　　　　　<!-- マウスを上に持ってくるとz-indexが2->16に浮き出てくる設定 -->
                        <v-card
                        :elevation="hover ? 16 : 2"
                        >
　　　　　　　　　　　　<!-- 画面リンク(src)と画像色に傾斜をつける(gradient)、v-textで画像上にテキスト（card.title, card.skill） -->
                          <v-img
                            :src="card.src"
                            class="white--text align-end"
                            gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                            height="200px"
                          >
                            <v-card-title v-text="card.title"></v-card-title>
                            <v-card-text v-text="card.skill"></v-card-text>
                          </v-img>
                        </v-card>
                      </v-hover>
                    </a>
                    </v-col>
                </v-row>
                </v-card>
            </v-container>
    </div>
</template>
<script>
  export default {
    data: () => ({
      cards: [
        { title: 'Portfolio Page', skill: 'HTML×CSS×jQuery×Bootstrap', src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg', redirect_url: 'https://takahashitakuya031126.github.io/' ,flex: {cols: 12, sm: 6, md: 6}},
        { title: 'Business Website', skill: 'WordPress', src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg', redirect_url: 'https://taktakportfolio.xyz/' ,flex: {cols: 12, sm: 6, md: 6} },
        { title: 'MATOMETUBE', skill: 'Laravel', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', redirect_url: 'https://matometube.herokuapp.com/' ,flex: {cols: 12, sm: 6, md: 6} },
      ],
    }),
  }
</script>
<style>
</style>