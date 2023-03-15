<template>
  <div class="imageList">
    <div v-for="item in items" :key="item.id">
      <a href="{{ item.imgLink }}"><img :src="item.src" :alt="item.title" /></a>
      <a href="{{ item.imgLink }}"
        ><h3>{{ item.title }}</h3></a
      >
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
        src: "/src/assets/img/propagation-01.jpg",
        title: "日常老和尚的譯經志業1｜弘揚廣論，深耕教法沃土",
        imgLink:
          "https://www.bwpublish.com/feature/master-jih-chang-translation-vocation/propagation",
      },
      {
        id: 2,
        src: "/src/assets/img/education-01.jpg",
        title: "日常老和尚的譯經志業2｜高瞻遠囑，擘畫僧伽教育",
        imgLink:
          "https://www.bwpublish.com/feature/master-jih-chang-translation-vocation/education",
      },
      {
        id: 3,
        src: "/src/assets/img/contribution-01.jpg",
        title: "日常老和尚的譯經志業3｜承先啟後，擎舉當代譯場",
        imgLink:
          "https://www.bwpublish.com/feature/master-jih-chang-translation-vocation/contribution",
      },
      {
        id: 4,
        src: "/src/assets/img/translation-forum-01-01.jpg",
        title: "【譯場古今】玄奘大師──遠紹如來，近光遺法",
        imgLink:
          "https://www.bwpublish.com/buddha-teachings/vision/translation-forum-01",
      },
      {
        id: 5,
        src: "/src/assets/img/translation-forum-02-01.jpg",
        title: "【譯場古今】鳩摩羅什大師──佛法泰斗，譯經津梁",
        imgLink:
          "https://www.bwpublish.com/buddha-teachings/vision/translation-forum-02",
      },
      {
        id: 6,
        src: "/src/assets/img/translation-forum-03-01.jpg",
        title: "【譯場古今】法尊法師──發願譯經，至死不悔",
        imgLink:
          "https://www.bwpublish.com/buddha-teachings/vision/translation-forum-03",
      },
    ]);

    return { items };
  },
};
</script>

<style scoped>
/* .imageList div {
  display: flexbox;
} */
/* .container {
  background-color: #1d1815;
  flex-direction: column;
  width: 100%;
}
.imageList {
  width: calc(100% - 20px);
  margin: 10px;

  padding: 20px;
  box-sizing: border-box;
} */

.imageList img {
  max-width: 50%;
}

/* @media screen and (max-width: 768px) {
  .imageList {
    width: 100%;
    margin: 10px 0;
  }
} */
</style>
