<template>
  <div class="presale">
    <TheRow class="title"
      ><h1>《廣論》奢摩他三經典 福智文化 12/6 殊勝出版</h1></TheRow
    >
    <TheRow class="subtitle">
      <TheCol class="sub-left">預購方案，即刻啟動</TheCol>
      <TheCol class="sub-right">
        2021.11.08—2021.12.05 請於各研討班．全省里仁門市、天天里仁網站登記預購
      </TheCol>
    </TheRow>
    <div>
      <PreSaleItem></PreSaleItem>
    </div>
  </div>
</template>

<script>
import PreSaleItem from "./PreSaleItem.vue";
import TheCol from "./TheCol.vue";
import TheRow from "./TheRow.vue";
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
  text-align: left;
  font-size: 22px;
  font-weight: 800;
}

.sub-left {
  margin: 0 20px 0 15px;
  color: #fff;
  background-color: #6a142a;
  padding: 5px 20px;
}

.sub-right {
  color: #6a142a;
  padding: 5px 20px 0;
}
</style>
