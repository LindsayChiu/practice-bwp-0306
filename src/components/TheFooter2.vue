<template>
  <footer class="footer">
    <div class="container">
      <span class="text-left">&copy; 版權所有‧2021福智文化股份有限公司 </span>
      <span class="text-right"
        ><a href="https://www.bwpublish.com/">聯絡我們</a></span
      >
    </div>
  </footer>
</template>

<style scoped>
.footer {
  position: relative;
  box-sizing: border-box;
  padding: 24px 0;
  bottom: 0;
  width: 100%;
  height: auto;
  line-height: 1.5rem;
  background-color: #5b5250;
}

.container {
  width: 100%;
  margin: 0 auto;
  text-align: center;
  font-size: 0.9rem;
  color: #fff;
}

.text-left {
  float: left;
  margin-left: 10%;
}

.text-right {
  float: right;
  margin-right: 10%;
}

@media screen and (max-width: 767px) {
  .container {
    line-height: 1.5rem;
    text-align: center;
    display: flex;
    flex-direction: column;
  }
  .text-left {
    display: block;
    margin: auto;
    order: 2;
  }

  .text-right {
    display: block;
    margin: auto;
    order: 1;
  }
}
</style>
