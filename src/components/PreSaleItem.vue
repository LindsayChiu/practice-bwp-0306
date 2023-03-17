<template>
  <div class="presaleitem">
    <div class="presalecol" v-for="item in items" :key="item.id">
      <img
        class="itemimg"
        :src="item.img"
        :alt="item.title"
        @load="setColWidth($event.target)"
      />
      <p class="itemtitle">{{ item.title }}</p>
      <ul class="itemul">
        <li
          class="itemli"
          v-for="contentItem in item.content"
          :key="contentItem"
        >
          {{ contentItem }}
        </li>
      </ul>
      <p class="pricetitle">
        {{ item.pricetitle }}<span class="spandis">NT${{ item.pricedis }}</span
        ><span class="spanorg">&#40;原價NT$</span
        ><span class="spandelete">{{ item.priceorg }} </span
        ><span class="spanorg">&#41;</span>
      </p>
      <p class="itemgift">{{ item.gift }}</p>
      <a :href="item.url"><button class="placeorder">我要請購 →</button></a>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const items = ref([
      {
        id: 1,
        img: "/src/assets/img/Solution-1.jpg",
        title: "預購方案１‧書盒版 雙經典組合",
        content: [
          "《菩提道次第廣論四家合註白話校註集5・奢摩他》 單書請購價 NT$1200",
          "《菩提道次第廣論・奢摩他》校訂本 單書請購價 NT$350",
        ],
        pricetitle: "雙經典套書預購價",
        pricedis: "1200",
        priceorg: "1550",
        gift: "贈品：恭敬經典．金剛力心咒貼紙",
        url: "https://bit.ly/3mpu0a8",
      },
      {
        id: 2,
        img: "/src/assets/img/Solution-2.jpg",
        title: "預購方案２‧三部經典精進組合",
        content: [
          "《菩提道次第廣論四家合註白話校註集5・奢摩他》 單書請購價 NT$1200",
          "《菩提道次第廣論・奢摩他》校訂本 單書請購價 NT$350",
          "《廣論止觀初探》第一卷 單書請購價 NT$450",
        ],
        pricetitle: "三部經典精進預購價",
        pricedis: "1500",
        priceorg: "2000",
        gift: "贈品：恭敬經典．金剛力心咒貼紙",
        url: "https://bit.ly/3GxUMoI",
      },
    ]);
    return {
      items,
    };
  },
};
</script>

<style scoped>
.presalecol {
  height: 100%;
  color: #6a142a;
  border: 0.5px solid #00000020;
  border-radius: 0.25rem;
  background-color: #fff;
}

.itemimg {
  max-width: 100%;
  border-radius: 0.25rem 0.25rem 0 0;
}
.itemtitle {
  font-size: 1.1rem;
  font-weight: 800;
  display: block;
  text-align: left;
  padding: 5% 0 3% 5%;
}

.itemul {
  min-height: 160px;
}

.itemli {
  list-style-type: disc;
  list-style-position: inside;
  font-size: 0.8rem;
  line-height: 1rem;
  text-align: left;
  padding: 0% 5% 1% 5%;
}
.pricetitle {
  font-size: 1rem;
  display: block;
  color: #111;
  font-size: 18px;
  font-weight: 600;
  text-align: left;
  padding-left: 5%;
}

.spandis {
  font-size: 0.9rem;
  color: #6a142a;
  font-weight: 600;
  padding-left: 2%;
  padding-right: 2%;
}

.spanorg {
  font-size: 1.1rem;
  color: #5b5250;
  font-size: 14px;
}

.spandelete {
  color: #6a142a;
  text-decoration: line-through;
  font-size: 14px;
}

.itemgift {
  color: #5b5250;
  text-align: left;
  padding-left: 5%;
  font-size: 0.8rem;
  padding-bottom: 4%;
  padding-top: 1%;
}

.placeorder {
  color: #fff;
  background-color: #6a142a;
  padding: 3% 20%;
  border: none;
  border-radius: 0.25rem;
  margin-bottom: 5%;
  margin-left: 5%;
  display: block;
  width: 90%;
  cursor: pointer;
}

@media screen and (min-width: 768px) {
  .presaleitem {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 30px;
  }
}
</style>
