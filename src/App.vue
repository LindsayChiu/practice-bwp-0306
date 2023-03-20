<script>
import NavBar from "./components/NavBar.vue";
import Banner from "./components/Banner.vue";
import Slogan2 from "./components/Slogan2.vue";
import TheFooter2 from "./components/TheFooter2.vue";
import OtherInfo from "./components/OtherInfo.vue";
import PreSale from "./components/PreSale.vue";
import Book from "./components/Book.vue";

export default {
  components: {
    NavBar,
    Banner,
    Slogan2,
    Book,
    PreSale,
    OtherInfo,
    TheFooter2,
  },
};
</script>

<template>
  <NavBar />
  <Banner />
  <Slogan2 />
  <Book />
  <PreSale />
  <OtherInfo />
  <TheFooter2 />
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  align-items: center;
  text-align: center;
}

html {
  font-family: Helvetica, Arial, sans-serif;
  font-size: 1rem;
  font-weight: 400;
  line-height: 1.5;
}

body > * {
  width: 100%;
  height: 100%;
  overflow-y: auto;
  overflow-x: hidden;
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
  cursor: pointer;
  align-items: center;
}

img {
  max-width: 100%;
  vertical-align: middle;
  border-style: none;
  overflow: clip;
  overflow: hidden;
}
</style>
