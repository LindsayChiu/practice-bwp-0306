<template>
  <TheRow>
    <TheCol v-for="item in items" :key="item.id">
      <a :href="item.imgLink">
        <img
          :src="item.src"
          :alt="item.title"
          @load="setColWidth($event.target)"
        />
      </a>
      <a :href="item.imgLink">{{ item.title }} </a>
    </TheCol>
  </TheRow>
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
