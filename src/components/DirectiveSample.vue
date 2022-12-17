<script>
export default {
  name: "DirectiveSample",
  data() {
    return {
      bases: [
        { 
          id: 1,
          th: 9,
          genre: "CML",
          cc: "ネクロx1、ベビx1、アチャx8",
          memo: "フリスタカップ用に作成した配置。罠で入りを崩すコンセプト",
          usedCount: 3,
          defensedCount: 2,
          imgUrl: "",
          baseLink: "https://link.clashofclans.com/en?action=OpenLayout&id=TH5%3AHV%3AAAAAKwAAAAIC-eLZwru3BgS7p13XOEK4",
          createdAt: "2022-12-11(Sun) 23:00",
          updatedAt: "2022-12-11(Sun) 23:00"
        },
        { 
          id: 2,
          th: 9,
          genre: "JWC9",
          cc: "ネクロx2、アチャx6",
          memo: "R杯用に作成した配置。広めに作成してドラがバラけたり黒爆弾で減るように意識した。",
          usedCount: 2,
          defensedCount: 2,
          imgUrl: "",
          baseLink: "",
          createdAt: "2022-12-11(Sun) 23:00",
          updatedAt: "2022-12-11(Sun) 23:00"
        },
        { 
          id: 3,
          th: 15,
          genre: "レジェンド",
          cc: "アイゴレx3、アチャx5",
          memo: "15初めての自作配置。意外と防衛率が高い",
          usedCount: 10,
          defensedCount: 7,
          imgUrl: "",
          baseLink: "",
          createdAt: "2022-12-11(Sun) 23:00",
          updatedAt: "2022-12-11(Sun) 23:00"
        },
      ]
    }
  },
  computed: {
    basedFilteringTH9 () {
      return this.bases.filter(b => b.th == 9);
    }
  }
}
</script>

<template>
  <div class="directiveSample">
    <h1>Directive Sample</h1>
    <h3>for-sample</h3>
    <ul v-for="b in bases">
      <li> id:{{ b.id }}, TH:{{ b.th }}, 種別:{{ b.genre }}, 援軍:{{ b.cc }}, メモ:{{ b.memo }}</li>
    </ul>
  </div>
</template>