<template>
    <div id="profile">
        <v-container
        fluid>
            <v-card
            width="100vw"
            >
            <v-card-title
            class="pa-5 justify-center display-1 font-italic"
            >
                Profile
            </v-card-title>

            <v-row
            justify="center"
            align-content="center"
            >
                <!-- レスポンシブ（スマホ(cols)：横いっぱい表示(MAX:12), PC・タブレット(sm,md):5/12）つまりアバター＆リスト横並びで表示 -->
                <v-col
                  cols="12"
                  sm="5"
                  md="5"
                  align="center"
                >
                <!-- justify: space-around横均等配置, align-content: center上下中央配置 -->
                <v-row
                justify="space-around"
                align-content="center"
                style="height:100%"
                >                
                <!-- v-avatar:アバター表示  -->
                <v-avatar
                width="80%"
                height="auto"
                >
                <!-- objet-fit:cover 画像中央トリミング表示。static/imageに配置した画像を参照  -->
                <img
                  src="/image/my-portfolio-profile.jpg"
                  alt="TAKTAK"
                  style="object-fit: cover;"
                >
                </v-avatar>
                </v-row>
                </v-col>
                <!-- レスポンシブ（スマホ(cols)：横いっぱい表示(MAX:12), PC・タブレット(sm,md):6/12） -->
                <v-col
                  cols="12"
                  sm="6"
                  md="6"
                >
                <!-- v-list:リスト表示、v-forでdataのobject(profiles)数分要素繰り返し描画  -->
                <v-list>
                    <v-list-item
                    v-for="profile in profiles"
                    :key="profile.content"
                    >
                      <v-list-item-content>
                      <!-- profileの中身（content）を表示。<v-icon>mdi-check</v-icon>でチェックアイコン表示  -->
                        <v-list-item-title><v-icon>mdi-check</v-icon> {{ profile.content }}</v-list-item-title>
                      </v-list-item-content>
                    </v-list-item>
                </v-list>
                </v-col>
            </v-row>
            </v-card>
        </v-container>
    </div>
</template>
<script>
  export default {
    data: () => ({
      profiles: [
        { content: '高橋 拓也（たかはしたくや）'},
        { content: '1991年東京生まれ'},
        { content: 'Webエンジニア'},
        { content: 'プログラミングと読書好き'},
        { content: 'インドカレー狂'},
        { content: '海外文学が好き'},
        { content: '生まれも育ちも八王子'},
        { content: 'マイペース'},
        { content: 'ゆとり世代'},
        { content: '英語は日常会話レベル'},
        { content: 'ITパスポート試験合格者'},
      ],
    }),
  }
</script>
<style>
</style>