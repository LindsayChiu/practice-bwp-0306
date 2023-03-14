<script setup>
import YoutubePlayer from "./YoutubePlayer.vue";
</script>

<template>
  <div class="background">
    <div class="container">
      <div class="row">
        <div class="slogan">
          <img
            src="../assets/img/Slogan.png"
            alt="slogan"
            class="slogan-slogan"
          />
          <img
            src="../assets/img/GoldStroke.png"
            alt="deco"
            class="slogan-deco"
          />
        </div>
      </div>
      <div class="video-container">
        <div class="video">
          <YoutubePlayer :videoId="'vOLr8FcAh-A'" />
        </div>
        <p class="videoinfo">
          福智團體創辦人上日下常老和尚自1982年起發心弘揚《廣論》，
          近40年來，《廣論》學修者遍布海內外各地，2000年，真如老師值遇了老和尚，
          殷重地祈求老和尚詳講《廣論》的止觀二章，然因眾弟子因緣尚不成熟，始終未能廣講。
          老和尚晚年將宣講《廣論》止觀章之重任囑咐老師。<br /><br />
          2020年10月15日真如老師謹遵師志，正式開講「廣論止觀初探」，
          依循《四家合註》及五大論等教理，帶領僧俗弟子逐字逐句研討《廣論》止觀章的內涵。<br /><br />
          值此殊勝因緣，為利大眾學習，福智文化於2021年12月6日隆重出版止觀學習教典——
          《菩提道次第廣論四家合註白話校註集5・奢摩他》、
          《菩提道次第廣論・奢摩他》校訂本、 《廣論止觀初探》第一卷。<br /><br />
          藉此獻給所有志求菩提道的人們，善巧駕馭寂止奢摩他的駿馬，
          手持中觀正見的鋒利寶劍，出征輪迴之城，摧破一切邊執所執境，奔赴那無死空性的光明國城！
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.background {
  display: flex;
  flex-wrap: wrap;
  overflow: hidden;
  background-image: url("../assets/img/video-background.jpg");
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
}
.container {
  display: block;
  position: relative;
  width: 100%;
  height: auto;
  padding: 0px 15px;
  align-items: center;
  justify-content: center;
}

.slogan {
  margin-left: 38vw;
  flex-basis: 0;
  max-width: 100%;
  padding: 0 15px;
}
.slogan-slogan {
  flex-grow: 1;
  padding: 80px 0 0;
  width: 18vw;
  min-width: 150px;
}

.slogan-deco {
  width: 15vw;
  min-width: 150px;
  position: absolute;
  top: 0;
}

.video-container {
  box-sizing: border-box;
  background-image: url("../assets/img/Reel.png");
  background-position: center;
  background-size: 100%;
  background-repeat: no-repeat;
  margin-top: 30px;
}
.video {
  padding: 22% 0 5%;
}
.videoinfo {
  height: auto;
}

@media screen and (min-width: 996px) {
  .video-container {
    padding: 2% 16% 4% 19%;
  }

  .videoinfo {
    font-size: 1rem;
    line-height: 1.5rem;
  }
}

/* 平板電腦版樣式  */
@media screen and (min-width: 768px) and (max-width: 996px) {
  .video-container {
    padding: 2% 16% 4% 19%;
  }

  .videoinfo {
    font-size: 0.9rem;
    line-height: 1.23rem;
  }
}

/* 手機版樣式 */
@media screen and (max-width: 767px) {
  .slogan {
    margin-left: 30vw;
  }
  .video-container {
    box-sizing: border-box;
    background-image: url("../assets/img/Reel-mob.png");
    background-position: top;
    background-size: 100%;
    background-repeat: no-repeat;
    margin-top: 30px;
  }
  .video-container {
    padding: 1% 18% 4% 19%;
  }

  .videoinfo {
    font-size: 0.8rem;
    line-height: 1.1rem;
  }
}
</style>
