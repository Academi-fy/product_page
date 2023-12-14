<template>

  <div class="signature">
    <div class="signature-text">
      <p>Developed with </p>
      <p class="names"> by <a target="_blank" href="https://github.com/Daanieeel">Daniel</a> & <a target="_blank" href="https://github.com/LxiniG">Linus</a></p>
    </div>
    <img class="red-heart" src="@/assets/images/red-heart.png" alt="Herz">
  </div>

</template>

<style scoped>
.signature {
  display: flex;
  justify-content: center;
  align-items: center;
  background: var(--primary);
  border-radius: 15px;
  color: var(--light);
  padding: 0.5rem 1rem;
  border: 2px solid rgba(0, 0, 0, 0.1);
}

.signature .red-heart {
  height: 2rem;
  width: 2rem;
}

.signature p {
  font-size: 0.8rem;
  opacity: 1;
}

.signature p a {
  font-weight: bold;
}

.signature p.names {
  font-size: 0.7rem;
}

.white-names .signature-text p a {
  color: var(--light);
  text-decoration: underline;
}
</style>