<template>
  <nav class="navbar">
    <div class="logo">
      <img src="/src/assets/photo/bw-logo.png" alt="logo" />
    </div>
    <div class="menu" :class="{ active: menuOpen, mobile: isMobile }">
      <a v-for="item in items" :key="item.alt" :href="item.url">
        <img v-if="item.img" :src="item.img" :alt="item.alt" />
        <span v-else>{{ item.text }}</span>
      </a>
    </div>
    <div class="toggle" @click="toggleMenu" :class="{ active: menuOpen }">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </nav>
</template>

<script>
import { ref, computed, watchEffect } from "vue";
import lineIcon from "../assets/photo/Line_white.png";

export default {
  setup() {
    const items = ref([
      {
        img: lineIcon,
        alt: "lineIcon",
        url: "https://example.com/1",
      },
      {
        img: lineIcon,
        alt: "lineIcon",
        url: "https://example.com/2",
      },
      {
        img: lineIcon,
        alt: "lineIcon",
        url: "https://example.com/3",
      },
      {
        text: "登入|註冊",
        url: "https://example.com/login",
      },
    ]);

    const isMobile = computed(() => {
      return window.innerWidth <= 768;
    });

    watchEffect(() => {
      const handleResize = () => {
        isMobile.value = window.innerWidth <= 768;
      };
      window.addEventListener("resize", handleResize);
      return () => {
        window.removeEventListener("resize", handleResize);
      };
    });

    const menuOpen = ref(false);

    const toggleMenu = () => {
      if (isMobile.value) {
        menuOpen.value = !menuOpen.value;
      }
    };

    const toggleActive = (menu) => {
      items.value.forEach((i) => (i.active = false));
      menu.active = true;
    };

    return {
      items,
      menuOpen,
      toggleMenu,
      toggleActive,
    };
  },
};
</script>

<style scoped>
.navbar {
  position: fixed;
  z-index: 9999;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px;
  background-color: #00000088;
}

.logo img {
  width: 25px;
  min-height: 25px;
}
.menu {
  display: flex;
}

.menu a img {
  height: 25px;
  width: 25px;
}
.menu a {
  margin-right: 15px;
  font-size: 16px;
}

.toggle {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 30px;
  height: 21px;
  cursor: pointer;
}

.toggle span {
  display: block;
  height: 3px;
  background-color: #fbf8f8ef;
  transition: transform 0.2s ease-in-out;
}

@media (max-width: 768px) {
  .menu {
    display: flex;
    /* transition: transform 0s ease-in-out; */
    transform: translateY(-150%);
  }
  .menu.active {
    transition: transform 0.8s ease-in-out;
    transform: translateY(180%);
  }
  .menu.mobile {
    display: none;
  }

  .toggle {
    display: flex;
    border: #fbf8f8ef 0.25px;
  }

  /* .toggle span:nth-child(2) {
    transform-origin: center;
  }

  .toggle.active span:nth-child(1) {
    transform: translateY(9px) rotate(45deg);
  }

  .toggle.active span:nth-child(2) {
    transform: rotate(-45deg);
  }

  .toggle.active span:nth-child(3) {
    transform: translateY(-9px) rotate(-45deg);
  } */
}
</style>
