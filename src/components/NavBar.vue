<script setup>
import { computed, onMounted, ref } from "vue";
import Logo from "@/assets/Logo.vue";

const scrollY = ref(0);
const isDarkMode = computed(() => window.matchMedia("(prefers-color-scheme: dark)").matches);
const scrollState = computed(() => scrollY.value > 0 ? (isDarkMode.value ? "rgba(0, 0, 0, 0.3)" : "rgba(255, 255, 255, 0.3)") : "transparent");
const linkColor = computed(() => scrollY.value > 0 ? "var(--secondary)" : "var(--light)");

onMounted(() => {
  window.addEventListener("scroll", () => {
    scrollY.value = window.scrollY;
  });
});
</script>

<template>

  <nav>
    <a href="#" class="logo-wrapper">
      <Logo/>
      <p id="logo-description">Academi.fy</p>
    </a>
    
    <ul>
      <li><a class="nav-link" href="#ueberblick">Überblick</a></li>
      <li><a class="nav-link" href="#web-untis">WebUntis</a></li>
      <li><a class="nav-link" href="#blackboards">Blackboards</a></li>
      <li><a class="nav-link" href="#events">Events</a></li>
    </ul>

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
  backdrop-filter: blur(20px);
}

nav ul {
  height: 100%;
  width: fit-content;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  gap: 2rem;
  flex-direction: row;
}

nav ul li {
  display: flex;
  justify-content: center;
  align-items: center;
}

nav ul li a {
  display: flex;
  justify-content: center;
  align-items: center;
  text-decoration: none;
  color: v-bind(linkColor);
  font-size: 1.2rem;
  font-weight: normal;
}

#logo {
  height: 4vh;
  width: 4vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.logo-wrapper {
  width: fit-content;
  display: flex;
  justify-content: start;
  align-items: center;
  gap: 1rem;
}

.logo-wrapper p {
  text-decoration: none;
  color: v-bind(linkColor);
  font-size: 1.2rem;
  font-weight: bold;
}

nav a:hover {
  background: none;
  color: var(--accent) !important;
}
</style>