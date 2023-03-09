<template>
  <div class="banner">
    <img :src="imageSrc" alt="Banner" />
  </div>
</template>

<style scoped>
.banner {
  max-width: 100%;
  height: auto;
}

.banner img {
  max-width: 100%;
  height: auto;
}

@media screen and (max-width: 768px) {
  .banner img {
    content: url("../assets/photo/banner-mob.jpg");
  }
}

@media screen and (min-width: 769px) {
  .banner img {
    content: url("../assets/photo/banner-pc.jpg");
  }
}
</style>

<script>
export default {
  name: "Banner",
  data() {
    return {
      imageSrc: "../assets/photo/banner-pc.jpg",
    };
  },
};
</script>
