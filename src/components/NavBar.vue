<script setup>
import { computed, onMounted, ref } from "vue";
import Logo from "@/assets/Logo.vue";
import NavLinksList from "@/components/NavLinksList.vue";
import NavLogo from "@/components/NavLogo.vue";

const scrollY = ref(0);
const isDarkMode = computed(() => window.matchMedia("(prefers-color-scheme: dark)").matches);
const scrollState = computed(() => scrollY.value > 0 ? (isDarkMode.value ? "rgba(0, 0, 0, 0.3)" : "rgba(255, 255, 255, 0.3)") : "transparent");
const linkColor = computed(() => scrollY.value > 0 ? "var(--secondary)" : "var(--light)");
const isBurgerMenuOpen = ref(false);

const toggleBurgerMenu = () => {
  isBurgerMenuOpen.value = !isBurgerMenuOpen.value;
};

onMounted(() => {
  window.addEventListener("scroll", () => {
    scrollY.value = window.scrollY;
  });
});
</script>

<template>
  <nav>
    <NavLogo v-bind:linkColor="linkColor"/>

    <NavLinksList
        v-bind:isBurgerMenuOpen="isBurgerMenuOpen"
        v-bind:linkColor="linkColor"
        class="standard-list"
    />

    <div class="burger-menu" v-bind:class="{ open: isBurgerMenuOpen }" v-show="isBurgerMenuOpen">
      <NavLinksList
          v-bind:isBurgerMenuOpen="isBurgerMenuOpen"
          v-bind:linkColor="linkColor"
          class="standard-list"
          @click="toggleBurgerMenu"
      />
    </div>

    <div class="burger-menu-button" @click="toggleBurgerMenu">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </nav>
</template>

<style scoped>
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 9svh;
  width: 100%;
  position: fixed;
  background-color: v-bind(scrollState);
  transition: background-color 0.2s ease-in-out;
  padding: 0 2rem;
  z-index: 10;
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
}

.burger-menu-button {
  display: none;
  flex-direction: column;
  justify-content: space-around;
  width: 1.5rem;
  height: 1.5rem;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0;
  z-index: 10;
}

.burger-menu-button span {
  width: 1.5rem;
  height: 0.2rem;
  background: v-bind(linkColor);
  border-radius: 10px;
  transition: all 0.3s linear;
  position: relative;
  transform-origin: 1px;
}

.burger-menu {
  display: none;
  flex-direction: column;
  align-items: end;
  background: rgba(var(--dark-rgba), 0.3);
  position: absolute;
  top: 0;
  right: 0;
  height: 100vh;
  width: 100vw;
  padding: 2rem;
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  transform: translateX(100%);
  transition: transform 0.3s ease-in-out;
}

.burger-menu.open {
  transform: translateX(0);
}

.burger-menu ul {
  margin-top: 9svh;
  list-style: none;
  padding: 0;
  display: flex;
  flex-direction: column;
  align-items: end;
  gap: 1rem;
}

.burger-menu ul li {
  font-size: 1.2rem;
  color: var(--secondary);
}

.burger-menu ul li a {
  text-decoration: none;
  color: inherit;
}

@media (max-width: 800px) {

  nav {
    padding: 1.5rem;
  }

  nav ul {
    justify-content: start;
  }

  .standard-list {
    display: none;
  }

  .burger-menu-button {
    display: flex;
  }

  .burger-menu {
    display: flex;
  }

}
</style>