<script setup>
import { onMounted, ref } from "vue";
import Logo from "@/assets/Logo.vue";

const scrollState = ref("transparent");

onMounted(() => {
  window.addEventListener("scroll", () => {
    if(window.scrollY > 0){
      scrollState.value = "var(--background)";
    } else {
      scrollState.value = "transparent";
    }
  });
})
</script>

<template>

  <nav>
    <a href="#" class="logo-wrapper">
      <Logo/>
      <p>Academi.fy</p>
    </a>
    
    <ul>
      <li><a href="#login">Login</a></li>
      <li><a href="#chats">Chats</a></li>
      <li><a href="#blackboards">Blackboards</a></li>
      <li><a href="#events">Events</a></li>
    </ul>

  </nav>

</template>

<style scoped>
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 10vh;
  width: 100%;
  position: fixed;
  background-color: v-bind(scrollState);
  transition: background-color 0.5s ease-in-out;
  padding: 0 2rem;
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
  color: var(--inversePrimary);
  font-size: 1.3rem;
}

#logo {
  height: 5vh;
  width: 5vh;
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
  color: var(--inversePrimary);
  font-size: 1.5rem;
  font-weight: bold;
}

nav a:hover {
  background: none;
  color: var(--inversePrimary);
}

</style>