<script setup>
import Logo from "@/assets/Logo.vue";
import { computed } from "vue";

const props = defineProps({
  linkColor: String
})
const linkColor = computed(() => props.linkColor);
</script>

<template>
  <a href="#" class="logo-wrapper">
    <Logo/>
    <p id="logo-description">Academi.fy</p>
  </a>
</template>

<style scoped>
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
</style>