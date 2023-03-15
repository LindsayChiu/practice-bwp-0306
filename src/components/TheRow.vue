<template>
  <div class="the-row">
    <slot></slot>
  </div>
</template>

<script>
import { ref, watch, onMounted, onUnmounted } from "vue";
import TheCol from "./TheCol.vue";

export default {
  name: "TheRow",

  components: { TheCol },

  setup() {
    const screenWidth = ref(window.innerWidth);
    const colCount = ref(1);

    const handleResize = () => {
      screenWidth.value = window.innerWidth;
    };

    watch(screenWidth, (newWidth) => {
      if (newWidth >= 1024) {
        colCount.value = 3;
      } else if (newWidth >= 768) {
        colCount.value = 2;
      } else {
        colCount.value = 1;
      }
    });

    onMounted(() => {
      window.addEventListener("resize", handleResize);
    });

    onUnmounted(() => {
      window.removeEventListener("resize", handleResize);
    });

    return {
      colCount,
    };
  },
  computed: {
    colWidth() {
      return `${100 / this.colCount}%`;
    },
  },
  methods: {
    setColWidth(el) {
      el.style.width = this.colWidth;
    },
  },
};
</script>

<style scoped>
.the-row {
  display: flex;
  flex-wrap: wrap;
  /* flex-direction: column; */
  margin: 0 -10px;
}

.the-row > * {
  padding: 0 10px;
  box-sizing: border-box;
}
</style>
