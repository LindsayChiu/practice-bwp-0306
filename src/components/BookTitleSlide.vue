<template>
  <div>
    <div class="title-container">
      <div class="title">
        <img :src="images[currentIndex].src" v-show="showImage" />
        <span>{{ titles[0] }}</span>
      </div>
      <div class="title">
        <img :src="images[currentIndex].src" v-show="showImage" />
        <span>{{ titles[1] }}</span>
      </div>
      <div class="title">
        <img :src="images[currentIndex].src" v-show="showImage" />
        <span>{{ titles[2] }}</span>
      </div>
    </div>
    <div class="button-container">
      <button @click="previousImage">Previous</button>
      <button @click="nextImage">Next</button>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "TitleComponent",
  props: {
    titles: {
      type: Array,
      required: true,
    },
    images: {
      type: Array,
      required: true,
    },
  },
  setup(props) {
    const currentIndex = ref(0);
    const showImage = ref(true);

    const previousImage = () => {
      currentIndex.value =
        (currentIndex.value - 1 + props.images.length) % props.images.length;
      showImage.value = !showImage.value;
    };

    const nextImage = () => {
      currentIndex.value = (currentIndex.value + 1) % props.images.length;
      showImage.value = !showImage.value;
    };

    return {
      currentIndex,
      showImage,
      previousImage,
      nextImage,
    };
  },
};
</script>

<style scoped>
.title-container {
  display: flex;
  justify-content: space-between;
}

.title {
  display: flex;
  align-items: center;
}

.title img {
  margin-right: 10px;
  max-width: 30px;
  max-height: 30px;
}

.button-container {
  display: flex;
  justify-content: center;
  margin-top: 20px;
}

button {
  margin: 0 10px;
}
</style>
