<script>
import moment from "moment"

export default {
  name: "DirectiveSample",
  data() {
    return {
      currentTime: moment().format("YYYY-mm-dd hh:mm"),
      bases: [
        { 
          id: 1,
          th: 9,
          genre: "CML",
          cc: "ネクロx1、ベビx1、アチャx8",
          memo: "フリスタカップ用に作成した配置。罠で入りを崩すコンセプト",
          usedCount: 3,
          defensedCount: 2,
          storageAt: { player: "七代虎徹", type: "野良", index: 3 },
          imgUrl: "https://firebasestorage.googleapis.com/v0/b/baselog-42f72.appspot.com/o/IMG_5737.PNG?alt=media&token=e43918c4-9059-4448-a624-157223e2236c",
          baseLink: "https://twitter.com/ktt5102",
          storageLimit: "2022-12-19 23:00:00",
        },
        { 
          id: 2,
          th: 9,
          genre: "JWC9",
          cc: "ネクロx2、アチャx6",
          memo: "R杯用に作成した配置。広めに作成してドラがバラけたり黒爆弾で減るように意識した。",
          usedCount: 2,
          defensedCount: 2,
          storageAt: { player: "八代虎徹", type: "対戦", index: 2 },
          imgUrl: "https://firebasestorage.googleapis.com/v0/b/baselog-42f72.appspot.com/o/IMG_4172.png?alt=media&token=65e977e5-3d94-4c03-af4a-e8d1f9680db2",
          baseLink: "https://twitter.com/clashofclansjp",
          storageLimit: "2022-12-19 23:30:00"
        },
        { 
          id: 3,
          th: 15,
          genre: "レジェンド",
          cc: "アイゴレx3、アチャx5",
          memo: "15初めての自作配置。意外と防衛率が高い",
          usedCount: 10,
          defensedCount: 7,
          storageAt: { player: "初代虎徹", type: "野良", index: 2 },
          imgUrl: "https://firebasestorage.googleapis.com/v0/b/baselog-42f72.appspot.com/o/IMG_5838.PNG?alt=media&token=c8ef612e-4f62-4e05-9068-100a802e3556",
          baseLink: "https://twitter.com/ktt5102",
          storageLimit: "2022-12-18 21:00:00"
        },
      ]
    }
  },
  created()  {
    setInterval(() => {
      this.currentTime = moment().format("YYYY-MM-DD HH:mm:ss"); 
    }, 1000)
  }, 
  computed: {
    basedFilteringTH9 () {
      return this.bases.filter(b => b.th == 9);
    }
  },
  methods: {
    getDiffSecond(fromTime, toTime) {
      let timeFrom = moment(fromTime);
      let timeTo = moment(toTime);
      return timeFrom.diff(timeTo, "seconds");
    },  
    getCountdown(anUpdatedAt) {
      let countDown = this.getDiffSecond(anUpdatedAt, this.currentTime);
      if (countDown > 0) {
        return countDown + "秒";
      } else {
        return "期限切れ";
      }
    }
  }
}
</script>

<template>
  <div class="directiveSample">
    <h1>Base Log</h1>
    <ul v-for="b in bases">
      <li><img class="baseImage" :src="b.imgUrl"/>TH:{{ b.th }}, 種別:{{ b.genre }}, 援軍:{{ b.cc }}, メモ:{{ b.memo }}, 保存先: {{ b.storageAt }}, リンク: <a v-bind:href="b.baseLink">click</a>, 期限まで: {{ getCountdown(b.storageLimit) }}</li>
    </ul>
  </div>
</template>

<style>
img.baseImage {
  width: 100%;
  object-fit: cover;
}
</style>

