<template>
  <div class="image-slider">
    <div class="info-container">
      <h2>{{ currentImageTitle }}</h2>
      <p>{{ currentImageDescription }}</p>
    </div>

    <div class="image-container">
      <img :src="currentImage" alt="Current Image" />
      <div class="controls-container">
        <button @click="previousImage">&#8249;</button>
        <button @click="nextImage">&#8250;</button>
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
        description: "This is the first image",
        src: "/src/assets/img/4-he-zhu.jpg",
      },
      {
        id: 2,
        title: "《菩提道次第廣論・奢摩他》校訂本",
        description: "This is the second image",
        src: "/src/assets/img/LR.jpg",
      },
      {
        id: 3,
        title: "《廣論止觀初探》第一卷",
        description: "This is the third image",
        src: "/src/assets/img/zhi-guan.jpg",
      },
    ]);

    const currentImage = computed(() => {
      return images.value[currentIndex.value].src;
    });

    const currentImageTitle = computed(() => {
      return images.value[currentIndex.value].title;
    });

    const currentImageDescription = computed(() => {
      return images.value[currentIndex.value].description;
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
      currentImageDescription,
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

.info-container {
  text-align: center;
  margin-bottom: 1rem;
  color: aliceblue;
  padding-right: 15px;
  padding-left: 15px;
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
</style>
