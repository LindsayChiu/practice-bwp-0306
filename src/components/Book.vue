<template>
  <div class="image-slider">
    <div class="pc-container">
      <div class="info-container">
        <span v-for="(image, index) in images" :key="image.id"
          ><img
            v-if="currentIndex === index"
            src="../assets/img/Indeicator.png"
          />{{ image.title }}</span
        >
      </div>

      <div class="image-container">
        <img :src="currentImage" alt="Current Image" />
        <div class="controls-container">
          <button @click="previousImage">&#8249;</button>
          <button @click="nextImage">&#8250;</button>
        </div>
        <a class="image-url" :href="currentImageUrl"> 更多詳細書籍資訊 → </a>
      </div>
    </div>
    <div class="mob-container">
      <div class="mob-img" v-for="image in images" :key="image.id">
        <img :src="image.srcMob" alt="Mob Image" />
        <a :href="image.url"> 更多詳細書籍資訊 → </a>
      </div>
    </div>
  </div>
</template>

<script>
import { ref, computed } from "vue";

export default {
  name: "ImageSlider",
  setup() {
    const currentIndex = ref(0);
    const images = ref([
      {
        id: 1,
        title: "《菩提道次第廣論四家合註白話校註集5・奢摩他》",
        src: "/src/assets/img/4-he-zhu.jpg",
        srcMob: "/src/assets/img/4hz-mob.jpg",
        url: "https://www.bwpublish.com/books/lrannotations-01-05",
      },
      {
        id: 2,
        title: "《菩提道次第廣論・奢摩他》校訂本",
        src: "/src/assets/img/LR.jpg",
        srcMob: "/src/assets/img/lr-mob.jpg",
        url: "https://www.bwpublish.com/books/lrannotations-serenity",
      },
      {
        id: 3,
        title: "《廣論止觀初探》第一卷",
        src: "/src/assets/img/zhi-guan.jpg",
        srcMob: "/src/assets/img/zg-mob.jpg",
        url: "https://www.bwpublish.com/books/serenity-insight-introduction-001",
      },
    ]);

    const currentImage = computed(() => {
      return images.value[currentIndex.value].src;
    });

    const currentImageTitle = computed(() => {
      return images.value[currentIndex.value].title;
    });

    const currentImageUrl = computed(() => {
      return images.value[currentIndex.value].url;
    });

    const nextImage = () => {
      currentIndex.value = (currentIndex.value + 1) % images.value.length;
    };

    const previousImage = () => {
      currentIndex.value =
        (currentIndex.value - 1 + images.value.length) % images.value.length;
    };

    return {
      currentIndex,
      images,
      currentImage,
      currentImageTitle,
      currentImageUrl,
      nextImage,
      previousImage,
    };
  },
};
</script>

<style>
.image-slider {
  background-color: #1d1815;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 40px 20px;
}

.info-container {
  font-size: 0.9rem;
  text-align: center;
  margin-bottom: 1rem;
  color: aliceblue;
  padding-right: 15px;
  padding-left: 15px;
  display: flex;
  align-items: stretch;
  justify-items: space-between;
  width: 100%;
}

.info-container img {
  display: flex;
  position: absolute;
  z-index: 999;
  margin-left: -4.5%;
  width: 26%;
}

.info-container span {
  flex: 1;
  padding-left: 7%;
  padding-right: 7%;
  border: 1px solid white;
  border-top: none;
  border-bottom: none;
}

.image-container {
  position: relative;
  width: 100%;
  padding-right: 15px;
  padding-left: 15px;
}

.image-container img {
  width: 100%;
  height: auto;
  object-fit: cover;
}

.controls-container {
  position: absolute;
  z-index: 999;
  width: 100%;
  display: flex;
  justify-content: space-between;
  left: 0;
  right: 0;
}

.controls-container button {
  background-color: transparent;
  color: #1d1815;
  border: none;
  font-size: 1.5rem;
  opacity: 0.7;
  margin-right: 20px;
  margin-left: 22px;
  margin-top: -42%;
}

.controls-container button:hover {
  background-color: transparent;
  color: #534740;
  cursor: pointer;
}

.image-url {
  color: #6a142a;
  font-size: 0.7rem;
  font-weight: 600;
  position: absolute;
  z-index: 999;
  width: 100%;
  display: flex;
  margin-left: 55px;
  margin-top: -10%;
}

@media screen and (min-width: 996px) {
  .mob-container {
    display: none;
  }
}

@media screen and (min-width: 768px) and (max-width: 996px) {
  .info-container {
    display: none;
  }
  .mob-container {
    display: none;
  }
}

@media screen and (max-width: 767px) {
  .pc-container {
    display: none;
  }

  .mob-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .mob-container img {
    width: 100%;
    padding: 15px;
  }

  .mob-container a {
    color: #6a142a;
    font-size: 0.9rem;
    font-weight: 600;
    display: flex;
    position: absolute;
    margin-top: -15%;
    padding-left: 9%;
  }
}
</style>
