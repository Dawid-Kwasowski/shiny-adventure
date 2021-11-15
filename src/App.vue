<template>
  <div class="wrapper">
    <section class="wrapper__navigation-panel navigation-panel">
      <div class="navigation-panel__logo">
        <img src="../src/assets/images/KOLOR.png" alt="logo">
      </div>
      <nav-bar></nav-bar>
    </section>
    <main class="main-content">
      <intro sectionID="about"></intro>
      
      <web-section sectionID="services" :hero="false" :darkMode="true">
        <template #body>
          <slider></slider>
        </template>
      </web-section>
      <locations></locations>

      <web-section sectionID="price">
        <template #header>
          <h1>{{sectionTitles[2]}}</h1>
        </template>
        <template #body>
          <dropdown @selectList="sendToService"></dropdown>
          <service-list :serviceList="currentServiceList"></service-list>
        </template>
      </web-section>

      <!-- <web-section sectionID="contact" :darkMode="true">
        <template #header>
          <h1>{{sectionTitles[3]}}</h1>
        </template>
        <template #body>
          <Form/>
        </template>
      </web-section> -->
      
    </main>
    
    <FAB/>
    <footer-section sectionID="contact"></footer-section>
  </div>
</template>

<script>

import NavBar from "./components/NavBar.vue"
import Intro from "./components/Intro.vue"
import FAB from "./components/FAB.vue"
import WebSection from "./components/WebSection.vue"
import Locations from "./components/Locations.vue"
import Slider from "./components/Slider.vue"
import Dropdown from "./components/Dropdown.vue"
import ServiceList from "./components/ServiceList.vue"
// import Form from "./components/Form.vue"
import FooterSection from './components/FooterSection.vue'
export default {
  data() {
    return {
      sectionTitles: [
        'O nas',
        'Usługi',
        'Cennik',
        'Kontakt'
      ],
      currentServiceList: []
    }
  },
  name: 'App',
  components: {
    NavBar,
    Intro,
    FAB,
    WebSection,
    Locations,
    Slider,
    Dropdown,
    ServiceList,
    // Form,
    FooterSection
  },
  methods: {
    sendToService(payload) {
      this.currentServiceList = payload
      console.log(this.currentServiceList)
    }
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
    scroll-behavior: smooth ;
  }
  

   .navigation-panel {
     position: sticky;
     z-index: 4;
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
