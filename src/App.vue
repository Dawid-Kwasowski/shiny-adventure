<template>
  <div class="wrapper">
    <section class="wrapper__navigation-panel navigation-panel">
      <div class="navigation-panel__logo">
        <img src="../src/assets/images/KOLOR.png" alt="logo">
      </div>
      <nav-bar></nav-bar>
    </section>
    <main class="main-content">
      
      <intro></intro>

      <web-section :darkMode="true">
        <template #header>
          <h1>{{sectionTitles[0]}}</h1>
        </template>
        <template #body>
          <article class="web-section__content">
              <p class="web-section__description">{{sectionContents[0]}}</p>
          </article>
        </template>
      </web-section>
      <locations></locations>

    </main>
    <FAB/>
  </div>
</template>

<script>

import NavBar from "./components/NavBar.vue"
import Intro from "./components/Intro.vue"
import FAB from "./components/FAB.vue"
import WebSection from "./components/WebSection.vue"
import Locations from "./components/Locations.vue"
export default {
  data() {
    return {
      sectionTitles: [
        'O nas',
        'Lokalizacja'
      ],
      sectionContents: [
        'PRO CLEANING SERVICE - jest firmą wykorzystującą atestowane i bezpieczne dla ludzi i zwierząt środki chemiczne. Pracujemy na nowoczesnym sprzęcie przemysłowym takich firm jak Prochem,Karcher'
      ]
    }
  },
  name: 'App',
  components: {
    NavBar,
    Intro,
    FAB,
    WebSection,
    Locations
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@500;600;700&display=swap');

  * {
    box-sizing: border-box;
    padding: 0;
    margin: 0;
    font-family: 'Open Sans', sans-serif;
  }

   .navigation-panel {
     position: sticky;
     top: 0;
     left: 0;
     background: #fff;
     display: flex;
     justify-content: space-between;
     align-items: center;
     width: 100%;
     min-height: 60px;
     padding: 6px 20px;
     &__logo {
       width:60px;

       img {
         width: 100%;
       }
     }
   }
</style>
