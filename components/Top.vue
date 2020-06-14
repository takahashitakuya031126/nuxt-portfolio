<template>
    <div id="top">
        <v-container
        fluid>
            <v-card
            width="100vw" height="100vh"
            >
            <v-img
            class="white--text align-center text-center font-italic"
            :class="{'headline': $vuetify.breakpoint. smAndDown, 'display-1': $vuetify.breakpoint. mdAndUp}"
            src="/image/my-portfolio-top.jpg"
            >
　　　　　　　<!-- v-img内にpタグ配置で画像上に文字が表示 --> 
            <p>Takahashi Takuya's LP</p>
            <p>高橋拓也のポートフォリオサイト</p>
            </v-img>
            </v-card>
        </v-container>
    </div>
</template>