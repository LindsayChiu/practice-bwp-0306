<template>
  <div class="youtube-player">
    <iframe
      :src="embedUrl"
      frameborder="0"
      allowfullscreen
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    ></iframe>
  </div>
</template>

<script>
import { ref, computed } from "vue";

export default {
  name: "YoutubePlayer",
  props: {
    videoId: {
      type: String,
      required: true,
    },
  },
  setup(props) {
    const embedUrl = computed(
      () => `https://www.youtube.com/embed/${props.videoId}`
    );

    return {
      embedUrl,
    };
  },
};
</script>

<style>
.youtube-player {
  position: relative;
  width: 100%;
  height: 0;
  padding-bottom: 56.25%; /* 16:9 aspect ratio */
}

.youtube-player iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
</style>
