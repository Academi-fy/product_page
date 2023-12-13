<script setup>
import NavBar from "@/components/NavBar.vue";
import Footer from "@/components/Footer.vue";
import WelcomeBlurryBackground from "@/components/WelcomeBlurryBackground.vue";
import BackToTopArrow from "@/components/BackToTopArrow.vue";
import Signature from "@/components/Signature.vue";
</script>

<template>

  <BackToTopArrow/>

  <body>
    <NavBar/>

    <section class="info" id="welcome">

      <div class="text-wrapper">
        <h2>Efficient Communication, the <span>crucial key</span> for Education Environments</h2>
        <p>Das Kommunikationsnetzwerk für Bildungseinrichtungen</p>
        <Signature/>
      </div>

      <WelcomeBlurryBackground class="background"/>

    </section>
    <section class="info" id="login">

    </section>
    <section class="info" id="chats">

    </section>
    <section class="info" id="blackboards">

    </section>
    <section class="info" id="events">

    </section>

    <Footer/>
  </body>

</template>

<style scoped>
#welcome{
  height: 150svh;
  display: flex;
  justify-content: center;
}

#welcome .background {
  position: absolute;
}

#welcome h2 {
  z-index: 1;
  font-size: 3rem;
  color: var(--inversePrimary);
  text-align: center;
  font-weight: 400;
  max-width: 1000px;
}

#welcome h2 span {
  font-family: 'Kalnia', serif;
  font-weight: 600;
}

#welcome .text-wrapper {
  height: fit-content;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: var(--inversePrimary);
  gap: 1rem;
  margin-top: 20vh;
}

#welcome .text-wrapper p {
  opacity: 0.5;
}

section.info{
  background-color: var(--background);
  height: 50svh;
  display: flex;
}

</style>
