<template>
  <div class="the-row">
    <slot></slot>
  </div>
</template>

<script>
import { ref, computed, watchEffect, onMounted, onUnmounted } from "vue";
import TheCol from "./TheCol.vue";

export default {
  name: "TheRow",

  components: { TheCol },

  props: {
    colCount: {
      type: Number,
      default: 1,
    },
  },

  setup(props) {
    const screenWidth = ref(window.innerWidth);

    const handleResize = () => {
      screenWidth.value = window.innerWidth;
    };

    onMounted(() => {
      window.addEventListener("resize", handleResize);
    });

    onUnmounted(() => {
      window.removeEventListener("resize", handleResize);
    });

    const colCount = computed(() => {
      if (screenWidth.value >= 1024) {
        return 3;
      } else if (screenWidth.value >= 768) {
        return 2;
      } else {
        return 1;
      }
    });

    const colWidth = computed(() => {
      return `${100 / colCount.value}%`;
    });

    const setColWidth = (el) => {
      el.style.width = colWidth.value;
    };

    watchEffect(() => {
      props.colCount = colCount.value;
    });

    return {
      colWidth,
      setColWidth,
    };
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
