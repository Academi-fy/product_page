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
  background-color: var(--background);
  border: none;
  outline: none;
  border-radius: 15px;
  z-index: 2;
  color: var(--inversePrimary);
  box-shadow: 4px 4px 8px 0 rgba(0, 0, 0, 0.2);
}

@media (width < 1500px) {
  #to-top {
    bottom: 1rem;
    right: 1rem;
  }
}

</style>