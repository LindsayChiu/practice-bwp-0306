<template>
  <div>
    <TheRow>
      <TheCol v-for="item in items" :key="item.id">
        <img
          :src="item.img"
          :alt="item.title"
          @load="setColWidth($event.target)"
        />
        <h2>{{ item.title }}</h2>
        <ul>
          <li v-for="contentItem in item.content" :key="contentItem">
            {{ contentItem }}
          </li>
        </ul>
        <h3>
          {{ item.pricetitle }}<span>" NT$ "{{ item.pricedis }}</span
          ><span>"&#40;原價NT$" {{ item.priceorg }} "&#41;"</span>
        </h3>
        <h4>{{ item.gift }}</h4>
      </TheCol>
    </TheRow>
  </div>
</template>

<script>
import { ref } from "vue";
import TheCol from "./TheCol.vue";
import TheRow from "./TheRow.vue";

export default {
  components: {
    TheRow,
    TheCol,
  },

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
      },
    ]);
    return {
      items,
    };
  },

  methods: {
    setColWidth(el) {
      el.style.width = this.$refs.row.colWidth;
    },
  },
};
</script>

<style scoped>
img {
  max-width: 100%;
}

div {
  text-align: left;
  padding: 15px;
}
</style>
