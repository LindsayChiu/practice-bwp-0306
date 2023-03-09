<script setup>
export default {
  components: {
    YoutubePlayer,
  },
};

import NavBar from "./components/NavBar.vue";
import Banner from "./components/Banner.vue";
import Slogan from "./components/Slogan.vue";
import YoutubePlayer from "./components/YoutubePlayer.vue";
</script>

<template>
  <NavBar />
  <Banner />
  <Slogan />
  <YoutubePlayer videoId="vOLr8FcAh-A" />
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-family: Helvetica, Arial, sans-serif;
  font-size: 1rem;
  font-weight: 400;
  line-height: 1.5;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-weight: normal;
  color: white;
}

li {
  list-style: none;
}

a {
  color: white;
  text-decoration: none;
  align-items: center;
}
</style>
