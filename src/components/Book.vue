<template>
  <div class="image-slider">
    <div class="info-container">
      <h2>{{ currentImageTitle }}</h2>
      <p>{{ currentImageDescription }}</p>
    </div>

    <div class="controls-container">
      <button @click="previousImage">Previous</button>
      <button @click="nextImage">Next</button>
    </div>

    <div class="image-container">
      <img :src="currentImage" alt="Current Image" />
    </div>
  </div>
</template>

<script>
export default {
  name: "ImageSlider",
  data() {
    return {
      currentIndex: 0,
      images: [
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
      ],
    };
  },
  computed: {
    currentImage() {
      return this.images[this.currentIndex].src;
    },
    currentImageTitle() {
      return this.images[this.currentIndex].title;
    },
    currentImageDescription() {
      return this.images[this.currentIndex].description;
    },
  },
  methods: {
    nextImage() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
    },
    previousImage() {
      this.currentIndex =
        (this.currentIndex - 1 + this.images.length) % this.images.length;
    },
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
  padding: 30px 20px;
}

.image-container {
  width: 100%;
  margin-top: 20px;
  margin-bottom: 20px;
  width: 100%;
  padding-right: 15px;
  padding-left: 15px;
}

.image-container img {
  width: 100%;
  height: auto;
  object-fit: cover;
  padding-right: 15px;
  padding-left: 15px;
}

.info-container {
  text-align: center;
  margin-bottom: 1rem;
  color: aliceblue;
  padding-right: 15px;
  padding-left: 15px;
}

.controls-container button {
  padding-right: 15px;
  padding-left: 15px;
}
</style>
