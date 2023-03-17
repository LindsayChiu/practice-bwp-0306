<template>
  <div class="presale">
    <TheRow class="title">
      <h1>《廣論》奢摩他三經典 福智文化 12/6 殊勝出版</h1>
    </TheRow>
    <TheRow class="subtitle">
      <div class="sub-left">預購方案，即刻啟動</div>
      <div class="sub-right">
        2021.11.08—2021.12.05 請於各研討班．全省里仁門市、天天里仁網站登記預購
      </div>
    </TheRow>
    <div class="presaleitem">
      <PreSaleItem></PreSaleItem>
    </div>
  </div>
</template>

<script>
import PreSaleItem from "./PreSaleItem.vue";
import TheCol from "./TheCol.vue";
import TheRow from "./TheRow.vue";

export default {
  components: {
    PreSaleItem,
    TheCol,
    TheRow,
  },
};
</script>

<style>
.presale {
  box-sizing: border-box;
  padding: 20px;
  width: 100%;
  background-image: url("../assets/img/presale-bg.png");
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}

.title h1 {
  color: #231815;
  padding: 10px 0 10px 10px;
  text-align: left;
  font-size: 1.4rem;
  font-weight: 800;
}

.subtitle {
  text-align: left;
  padding: 0 0 10px 0px;
  font-size: 0.8rem;
  line-height: 1.2rem;
}

.sub-left {
  margin: 0 20px 0 15px;
  color: #fff;
  background-color: #6a142a;
  padding: 5px 20px;
}

.sub-right {
  text-align: left;
  color: #6a142a;
  padding: 5px 20px 0;
}

/* .presaleitem {
  border: none;
} */
</style>
