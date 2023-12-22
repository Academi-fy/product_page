<script setup>
import NavLogo from "@/components/NavLogo.vue";

defineProps({
  isBurgerMenuOpen: Boolean
})
</script>

<template>

  <ul>
    <li v-if="isBurgerMenuOpen">
      <NavLogo linkColor="var(--light)"/>
    </li>
    <li><a class="nav-link" href="#ueberblick">Überblick</a></li>
    <li><a class="nav-link" href="#web-untis">WebUntis</a></li>
    <li><a class="nav-link" href="#blackboards">Blackboards</a></li>
    <li><a class="nav-link" href="#events">Events</a></li>
  </ul>

</template>

<style scoped>
ul {
  height: 100%;
  width: fit-content;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  gap: 2rem;
  flex-direction: row;
}

ul li {
  display: flex;
  justify-content: center;
  align-items: center;
}

ul li a {
  display: flex;
  justify-content: center;
  align-items: center;
  text-decoration: none;
  color: var(--light);
  font-size: 1.2rem;
  font-weight: normal;
}

a:hover {
  background: none;
  color: var(--accent) !important;
}

</style>