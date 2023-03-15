<template>
  <div ref="col" class="col">
    <slot></slot>
  </div>
</template>

<script>
import { onMounted, computed, ref } from "vue";

export default {
  setup(props, { emit }) {
    const col = ref(null);
    const colWidth = computed(() => {
      return col.value ? col.value.offsetWidth : 0;
    });

    onMounted(() => {
      emit("register-col", colWidth.value);
    });

    return {
      col,
    };
  },
};
</script>

<style scoped>
.col {
  padding: 15px;
  float: left;
  width: 100%;
}
@media (min-width: 768px) {
  .col {
    width: 50%;
  }
}
@media (min-width: 1024px) {
  .col {
    width: 33.333333%;
  }
}
</style>
