<template>
  <div class="wish">
    <div class="container-wish">
      <div class="row-container-wish">
        <div class="clo-container-wish"><span>師長的心願</span></div>
      </div>
      <div class="row-container-wish">
        <div class="clo-container-wish">
          <img class="tritonis" src="../assets/img/Tritonis.png" />
        </div>
      </div>

      <div class="row-imagelist">
        <div class="clo-container-wish">
          <ImageList></ImageList>
        </div>
      </div>

      <TheVideo />
    </div>
  </div>
</template>

<script setup>
import ImageList from "./ImageList.vue";
import TheVideo from "./TheVideo.vue";
</script>

<style scoped>
.wish {
  background-color: #1d1815;
  padding: 80px 0;
  box-sizing: border-box;
}
.container-wish {
  width: 100%;
  padding: 0 15px;
  /* margin-right: 40px;
  margin-left: 40px; */
}

.row-container-wish {
  display: flex;
  flex-wrap: wrap;
}

/* .row-imagelist {
  display: grid;
} */

.clo-container-wish {
  flex-basis: 0;
  flex-grow: 1;
  max-width: 100%;
  color: #fff;
  font-size: 16px;
}

.tritonis {
  width: 50px;
  margin: 30px 0;
}
</style>
