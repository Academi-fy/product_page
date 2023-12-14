<script setup>
import ArrowUpToLine from "./icons/ArrowUpToLine.vue";
import { onMounted, ref } from "vue";

const isScrolled = ref(false);
function toTop(){
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

onMounted(() => {
  window.addEventListener("scroll", () => {
    isScrolled.value = window.scrollY > 0;
  });
})
</script>

<template>

  <div>
    <button id="to-top" @click="toTop" v-if="isScrolled">
      <ArrowUpToLine/>
    </button>
  </div>

</template>

<style scoped>

#to-top {
  width: 70px;
  height: 70px;
  position: fixed;
  bottom: 2rem;
  right: 2rem;
  cursor: pointer;
  background-color: var(--secondary);
  border: none;
  outline: none;
  border-radius: 15px;
  z-index: 2;
  color: var(--primary);
  box-shadow: 4px 4px 8px 0 rgba(var(--dark), 0.2);
}

button#to-top:hover {
  background-color: var(--dark-off);
  transition: background-color 0.2s ease-in-out;
}

button#to-top:hover svg {
  transform: scale(1.3);
  transition: transform 0.2s ease-in-out;
}

@media (width < 1500px) {
  #to-top {
    bottom: 1rem;
    right: 1rem;
  }
}

</style>