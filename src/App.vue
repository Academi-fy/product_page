<script setup>
import NavBar from "@/components/NavBar.vue";
import Footer from "@/components/Footer.vue";
import WelcomeBlurryBackground from "@/components/WelcomeBlurryBackground.vue";
import BackToTopArrow from "@/components/BackToTopArrow.vue";
import Signature from "@/components/Signature.vue";

import { onMounted, onUnmounted, ref } from 'vue';
import ChevronDown from "@/components/icons/ChevronDown.vue";
import AddressBookSolid from "@/components/icons/AddressBookSolid.vue";
import CompassDraftingSolid from "@/components/icons/CompassDraftingSolid.vue";
import WandMagicSparklesSolid from "@/components/icons/WandMagicSparklesSolid.vue";
import PeoplePullingSolid from "@/components/icons/PeoplePullingSolid.vue";

let scrollPosition = ref(0);

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

function handleScroll() {
  scrollPosition.value = window.scrollY;
  if (scrollPosition.value > 0) { // Change this value to control when the animation should stop
    document.getElementById('web-app-chat-view').style.marginTop = `0rem`;
    console.log('scrolling');
    window.removeEventListener('scroll', handleScroll);
  }
}

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<template>

  <BackToTopArrow/>

  <body>
    <NavBar/>

    <section class="info" id="welcome">

      <div class="content-wrapper">
        <div class="text-wrapper">
          <h2>Efficient Communication, the <span class="cursive">crucial key</span> for Education Environments</h2>
          <p>Das Kommunikationsnetzwerk für Bildungseinrichtungen</p>
          <Signature class="white-names"/>
        </div>

        <a class="chevron-button" href="#ueberblick"><ChevronDown class="chevron-down"/></a>

        <img id="web-app-chat-view" src="@/assets/images/web-app-chat-view.png" alt="Academi.fy App auf einem MacBook">
      </div>

      <WelcomeBlurryBackground class="background"/>

    </section>

    <section class="info" id="ueberblick">

      <h2>Kleine <span class="cursive">Nachrichten</span>, große <span class="cursive">Ereignisse</span>: ein Ort!</h2>
      <p>Erlebe Schule auf eine neue Art: Mit aktuellen Events, frischen Infos und Live-Chats bringen wir Schulgemeinschaft direkt auf deinen Bildschirm.</p>

      <div class="table">

        <div class="table-item">
          <div class="item-heading">
            <AddressBookSolid/>
            <h3>Effiziente Kommunikation</h3>
          </div>
          <p>
            Academi.fy bietet blitzschnelle Chats und Echtzeitbenachrichtigungen für eine reibungslose und zeitnahe Interaktion zwischen Schülern,
            Lehrern und Administration.
          </p>
        </div>
        <div class="table-item">
          <div class="item-heading">
            <CompassDraftingSolid/>
            <h3>Moderne Benutzeroberfläche</h3>
          </div>
          <p>
            Mit einem frischen, intuitiven Design und benutzerfreundlichen Funktionen bietet Academi.fy ein zeitgemäßes Erlebnis für ein
            müheloses Kommunizieren und Arbeiten.
          </p>
        </div>
        <div class="table-item">
          <div class="item-heading">
            <PeoplePullingSolid/>
            <h3>Gemeinschaft erleben</h3>
          </div>
          <p>
            Wir fördern durch Einblicke in aktuelle Geschehnisse und Veranstaltungen kombiniert mit einer Plattform für direkten Austausch das gemeinsame Erleben
            des Schullebens. So geht moderne Schule!
          </p>
        </div>
        <div class="table-item">
          <div class="item-heading">
            <WandMagicSparklesSolid/>
            <h3>Interaktiver Aufbau</h3>
          </div>
          <p>
            Lerngruppen und AGs profitieren besonders von den kollaborativen News und Blackboards.
            In der dynamischen Informationszentrale finden sich vielfältige Angebote und Informationen.
          </p>
        </div>

      </div>

    </section>

    <section class="info mockup" id="web-untis">

      <div class="web-untis section login">
        <div class="text-wrapper">
          <h2>Einfacher Login: <span class="cursive">WebUntis</span></h2>
          <div class="paragraphs">
            <p>
              Wenn Du dich in der App anmeldest, gibst Du deine Schul-Login-Daten ein. Diese Informationen werden sicher an die <span class="cursive">WebUntis</span> Plattform
              gesendet, um sicherzustellen, dass sie korrekt sind. Bei erfolgreicher Überprüfung erhält die App eine Art digitales Ticket, das es ihr
              erlaubt, auf deine Schuldaten zuzugreifen.
            </p>
            <p>
              Diese Sicherheitsvorkehrungen gewährleisten, dass Nutzer-Daten geschützt sind, und nur der Nutzer Zugriff darauf hat. Die Kommunikation zwischen der
              App und WebUntis ist verschlüsselt, um die <span class="cursive">Privatsphäre</span> zu wahren.
            </p>
            <p>
              Für den Nutzer bedeutet das, Chats, Events und andere relevante Schulinfos mit dem bereits bestehenden WebUntis Zugang einsehen zu können,
              wobei alles durch Klassen und Kurse <span class="cursive">up-to-date</span> bleibt.
            </p>
          </div>
        </div>
        <img src="@/assets/images/mockup-login.png" alt="Handy mit der Login Seite von Academi.fy">
      </div>

      <div class="web-untis section chats">
        <div class="text-wrapper">
          <h2>Kommunikation in Echtzeit: <span class="cursive">Chats</span></h2>
          <div class="paragraphs">
            <p>
              Bei Academi.fy wird die direkte Kommunikation zwischen Lehrern und Schülern zu einem zentralen Bestandteil des
              <span class="cursive">Lernerlebnisses</span>. Kurse, Arbeitsgemeinschaften und private Gespräche bieten eine
              dynamische Plattform für den Austausch von Informationen und die Interaktion in <span class="cursive">Echtzeit</span>, um Fragen zu stellen,
              Ideen zu diskutieren oder einfach mit Lehrern und Mitschülern in Kontakt zu bleiben.
            </p>
            <p>
              Die Sicherheit Deiner persönlichen Daten steht dabei im Mittelpunkt. Die verschlüsselte Übertragung gewährleistet
              einen geschützten Austausch innerhalb der Chats, während du gleichzeitig Events und wichtige Informationen
              rund um Deine <span class="cursive">Klassen und Kurse</span> in Echtzeit einsehen kannst.
            </p>
          </div>
        </div>
        <img src="@/assets/images/mockup-chat-view.png" alt="Handy mit der Chat Seite von Academi.fy">
      </div>

    </section>
    <section class="info mockup" id="blackboards">

      <div class="text-wrapper">
        <h2>Kollaborativer Austausch: <span class="cursive">Blackboards</span></h2>
        <div class="paragraphs">
          <p>
            Ob Bücherausgabe, Elternbriefe oder Klassenfahrt: Mit den Blackboards von Academi.fy kein:e Schüler:in mehr etwas. Die dynamischen Artikel bieten eine Plattform für alle
            wichtigen <span class="cursive">Informationen</span> rund um die Schule. So bleiben alle auf dem neuesten Stand und können sich auf das Wesentliche konzentrieren:
            <span class="cursive">Lernen</span>.
          </p>
          <p>
            Die Blackboards können individuell für Klassen, Kurse oder Veranstaltungen erstellt werden, um die Kommunikation in der Schulgemeinschaft
            zu erleichtern. Blackboards sind ein Ort für alle relevanten Informationen und ein Mittel, um das <span class="cursive">Schulleben</span> zu erleben.
          </p>
        </div>
      </div>
      <img src="@/assets/images/mockup-blackboard-view.png" alt="Handy mit der Login Seite von Academi.fy">

    </section>
    <section class="info mockup" id="events">

      <div class="text-wrapper">
        <h2>Interaktive Gemeinschaft: <span class="cursive">Events</span></h2>
        <div class="paragraphs">
          <p>
            "Anstehend diesen Monat: nachgefragt, Weihnachtskonzert, Turmblasen und vieles mehr!". Die praktischen Events von Academi.fy bieten eine Plattform
            für <span class="cursive">Schulveranstaltungen</span> und Termine. Werbung am Schwarzen Brett war gestern!
          </p>
          <p>
            Durch die individuellen <span class="cursive">Push-Benachrichtigungen</span> bleiben Interessierte stets auf dem Laufenden. Während Events können Abonnenten des Events durch Push-Benachrichtigungen
            über Geschehnisse in <span class="cursive">Echtzeit</span> informiert werden. Außerdem gibt es eine Möglichkeit, Tickets bzw. Sitzplätze.
          </p>
        </div>
      </div>
      <img src="@/assets/images/mockup-events.png" alt="Handy mit der Login Seite von Academi.fy">

    </section>

    <Footer/>
  </body>

</template>

<style scoped>
section:not(section:first-of-type) {
  scroll-margin-top: 9svh;
}

.chevron-button:hover {
  transform: scale(2);
}

.cursive {
  font-family: 'Kalnia', serif;
  font-weight: 600;
  color: var(--secondary);
}

h2 {
  font-size: 3rem;
  font-weight: 800;
  color: var(--secondary);
  max-width: 1100px;
}

section.info{
  background-color: var(--primary);
  min-height: 50svh;
  height: fit-content;
  display: flex;
  flex-direction: row;
  justify-content: center;
  color: var(--secondary);
}

section.mockup img {
  max-height: 500px;
  object-fit: contain;
}

section.info:not(#welcome) {
  align-items: center;
}

#welcome{
  height: fit-content;
  display: flex;
  min-height: 100svh;
}

#welcome .cursive {
  color: var(--light);
}

#welcome .background {
  position: absolute;
}

#welcome .content-wrapper {
  padding-top: 15rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  gap: 5rem;
}

#welcome h2 {
  z-index: 1;
  color: var(--light);
  text-align: center;
  max-width: 1100px;
  width: 90%;
  font-weight: 600;
}

#welcome .text-wrapper {
  height: fit-content;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  color: var(--light);
  gap: 1rem;
}

#welcome .text-wrapper p {
  opacity: 0.75;
}

#welcome .signature{
  background-color: rgba(255, 255, 255, .15);
  backdrop-filter: blur(10px);
  border: none;
}

#welcome .content-wrapper img {
  max-width: 1200px;
  width: 70%;
  margin-top: 15rem;
  border-radius: 10px;
  box-shadow: 0 0 60px rgba(var(--secondary-rgba), 0.2);
  transition: margin-top 0.8s ease;
}

#welcome .chevron-down {
  color: var(--light);
}

#ueberblick {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 10rem;
  gap: 2rem;
  color: var(--secondary);
}

#ueberblick h2 {
  max-width: 25ch;
  width: 90%;
  text-align: center;
}

#ueberblick p {
  max-width: 60ch;
  width: 90%;
  text-align: center;
  opacity: 0.5;
}

#ueberblick .table {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr 1fr;
  gap: 1rem;
  margin-top: 2rem;
}

#ueberblick .table-item {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  padding: 2rem;
  border-radius: 10px;
  border: 1px solid var(--primary-off);
  transition: background-color 0.2s ease-in-out;
}

#ueberblick .table-item:hover {
  background-color: var(--accent);
  box-shadow: 5px 5px 2px rgba(var(--dark-off), 0.52);
  color: var(--light);
}

#ueberblick .table-item:hover > p {
  opacity: 1;
}

#ueberblick .table-item:hover > .item-heading svg{
  color: var(--light);
}

#ueberblick .table-item .item-heading {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
}

#ueberblick .table-item .item-heading h3 {
  font-size: 1.3rem;
  font-weight: 600;
}

#ueberblick .table-item svg {
  height: 1.5rem;
  width: 1.5rem;
  color: var(--accent);
  transition: color 0.2s ease-in-out;
}

#web-untis {
  display: flex;
  flex-direction: column;
  padding: 10rem;
  gap: 10rem;
}

.web-untis.login {
  display: flex;
  flex-direction: row;
  gap: 5rem;
}

.web-untis.section img {
  filter: drop-shadow(30px 30px 30px rgba(var(--secondary-rgba), 0.3));
  transition: margin-top 0.8s ease;
}

.web-untis.section .text-wrapper {
  display: flex;
  flex-direction: column;
  gap: 3rem;
}

.web-untis.section .text-wrapper .paragraphs {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.web-untis.section .text-wrapper p {
  color: rgba(var(--secondary-rgba), 0.8);
}

.web-untis.section .text-wrapper h2 {
  max-width: 16.5ch;
}

.web-untis.section.chats {
  display: flex;
  flex-direction: row-reverse;
  gap: 5rem;
}

.web-untis.section.chats img {
  filter: drop-shadow(-30px 30px 30px rgba(var(--secondary-rgba), 0.3));
}

section:not(#welcome, #ueberblick, #web-untis) {
  display: flex;
  flex-direction: row;
  padding: 10rem;
  gap: 10rem;
}

section:not(#welcome, #ueberblick, #web-untis) img {
  filter: drop-shadow(30px 30px 30px rgba(var(--secondary-rgba), 0.3));
  transition: margin-top 0.8s ease;
}

section:not(#welcome, #ueberblick, #web-untis) .text-wrapper {
  display: flex;
  flex-direction: column;
  gap: 3rem;
}

section:not(#welcome, #ueberblick, #web-untis) .text-wrapper .paragraphs {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

section:not(#welcome, #ueberblick, #web-untis) .text-wrapper p {
  color: rgba(var(--secondary-rgba), 0.8);
}

section:not(#welcome, #ueberblick, #web-untis) .text-wrapper h2 {
  max-width: 16.5ch;
}

section:last-of-type {
  padding-bottom: 10rem;
}

section#events  {
  flex-direction: row-reverse;
}

@media (max-width: 1300px) {

  h2 {
    font-size: 2.5rem;
  }

  section.info.mockup {
    flex-direction: column !important;
  }

  #web-untis div {
    flex-direction: column !important;
    align-items: center;
    justify-content: center;
  }

}

@media (max-width: 1100px) {

  h2 {
    font-size: 2rem;
  }

  section {
    padding: 3rem !important;
  }

  #ueberblick .table {
    grid-template-columns: 1fr;
  }

  #ueberblick .table-item .item-heading {
    flex-direction: column;
    justify-content: start;
    align-items: start;
  }

  #ueberblick .table-item p {
    text-align: justify;
  }

  #web-untis .section img {
    max-width: 90%;
  }

  section.mockup img {
    max-width: 90%;
  }

}

@media (max-width: 900px) {

  h2 {
    font-size: 1.5rem;
  }

  #web-app-chat-view {
    display: none;
  }

}

@media (max-width: 550px) {

  #welcome .content-wrapper .text-wrapper p {
    text-align: center;
  }

}

</style>
