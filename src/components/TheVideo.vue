<script setup>
import YoutubePlayer from "./YoutubePlayer.vue";
</script>

<template>
  <div class="the-video">
    <YoutubePlayer :videoId="'przyPZt2jrM'" />
  </div>
</template>

<style scoped>
.the-video {
  position: relative;
  box-sizing: border-box;
  padding: 10px;
  width: 100%;
  height: auto;
}
</style>
