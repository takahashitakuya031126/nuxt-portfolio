<template>
    <div id="history">
        <v-container
        fluid>
            <v-card
            width="100vw"
            class="pa-4"
            >
            <v-card-title
            class="justify-center display-1 font-italic"
            >
                History
            </v-card-title>

              <!-- タイムラインコンポーネント -->
              <v-timeline>
                <!-- タイムラインアイテム（経歴項目）、v-for:data(years)の要素分項目繰り返し、small:中央のDotのサイズを小さく -->
                <v-timeline-item
                  v-for="(year, i) in years"
                  :key="i"
                  :color="year.color"
                  small
                >
                  <!-- タイムラインの項目の方向を反転(opposite)、年数(year.year)とその色(year.color)を指定 -->
                  <template v-slot:opposite>
                    <span
                      :class="`title font-weight-bold ${year.color}--text`"
                      v-text="year.year"
                    ></span>
                  </template>
                  <!-- 項目のタイトル（year.title）テキスト(year.content)を指定 -->
                  <div class="py-4">
                    <h2 :class="`title font-italic mb-4 ${year.color}--text`">{{ year.title }}</h2>
                    <div>
                        {{ year.content }}
                    </div>
                  </div>
                </v-timeline-item>
              </v-timeline>
            </v-card>
        </v-container>

    </div>
</template>
<script>
  export default {
    data: () => ({
      // 経歴の項目データ
      years: [
        {
          color: 'cyan',
          year: '2010~14',
          title: '東京工科大学',
          content: 'メディア学部在籍'
        },
        {
          color: 'green',
          year: '2015~16',
          title: '二葉栄養専門学校',
          content: '調理師免許を取得するために1年間在籍。西洋料理の道をきわめようと志す'
        },
        {
          color: 'pink',
          year: '2015~19',
          title: '京王プラザホテル（新宿）',
          content: '西洋料理の宴会料理を担当'
        },
        {
          color: 'amber',
          year: '2019~20',
          title: 'ブックオフ',
          content: '古本や中古ゲームを販売。その後、IT業界に魅了され1年で転職'
        },
        {
          color: 'orange',
          year: '2020~',
          title: 'Webエンジニア',
          content: '今日も楽しくプログラミング'
        },
      ],
    }),
  }
</script>
<style>
</style>