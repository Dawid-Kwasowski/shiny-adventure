<template>
  <div class="wrapper">
    <div class="navigation-panel__info">
      <h3>Pracujemy 24/7 !</h3>
    </div>
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
          <dropdown v-if="!isDesktop" :services="services" @selectList="sendToService"></dropdown>
          <service-list v-if="!isDesktop" :serviceList="currentServiceList"></service-list>
          <desktop-service-list :services="services" v-else></desktop-service-list>
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
import DesktopServiceList from './components/DesktopServiceList.vue'
export default {
  data() {
    return {
      sectionTitles: [
        'O nas',
        'Usługi',
        'Cennik',
        'Kontakt' 
      ],
      services: [
            // '²' is for testing 
            {
               title: 'Kompleksowe sprzątanie domu/mieszkania',
               priceList: [
                  {meters: "< 50m²", price: "200-300 zł", info: ''},
                  {meters: "50-100m²", price: "300-400 zł",info: ''},
                  {meters: "100-150m²", price: "400-500 zł",info: ''},
                  {meters: "150-200m²", price: "500-600 zł",info: ''},
                  {meters: "200-250m²", price: " 600-700 zł",info: ''},
               ]
            },
            {
               title: 'Poremontowe sprzątanie domu/mieszkania',
               priceList: [
                  {meters: "< 50m²", price: "350-450 zł",info: ''},
                  {meters: "50-100m²", price: "450-650 zł",info: ''},
                  {meters: "100-150m²", price: "650-900 zł",info: ''},
                  {meters: "150-200m²", price: "900-1100 zł",info: ''},
                  {meters: "200-250m²", price: "1100-1500 zł",info: ''},
               ]
            },
            {
               title: 'Sprzątanie lokali po imprezach okolicznościowych',
               priceList: [{meters:'', price:'', info: 'Wycena Inwidualna'}]
            },
            {
               title: 'Sprzątanie biur',
               priceList: [{meters:'', price:'', info: 'Wycena Inwidualna'}]
            },
            {
               title: 'Mycie okien wraz z ramą i parapetem',
               priceList: [{meters:'', price:'', info: 'Cena za skrzydło od 15 zł'}]
            },
            {
               title: 'Mycie okien po remoncie wraz z ramą i parapetem',
               priceList: [{meters:'', price:'', info: 'Cena za skrzydło od 20 zł'}]
            },
            {
               title: 'Sprzątanie piwnic i garaży',
               priceList: [{meters:'', price:'', info: '240 zł za pomieszczenie'}]
            },
            {
               title: 'Pranie dywanów',
               priceList: [{meters:'', price:'', info: '8 - 12zł za metr'}]
            },
            {
               title: "Pranie foteli, kszeseł, puf itp",
               priceList: [{meters:'', price:'', info: 'od 40 zł'}]
            },
            {
               title: "Pranie sofy, narożnika",
               priceList: [{meters:'', price:'', info: 'od 120 zł'}]
            },
            {
               title: "Pranie tapicerki samochodowej",
               priceList: [{meters:'', price:'', info: 'od 180zł'}]
            },
            {
               title: "Pranie podsufitki",
               priceList: [{meters:'', price:'', info: 'od 50 zł'}]
            },
            {
               title: "Kompleksowe sprzątanie aut",
               priceList: [{meters:'', price:'', info: '130zł / 160zł'}]
            },
         ],
      isDesktop: matchMedia("(min-width:1024px)").matches,
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
    FooterSection,
    DesktopServiceList
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

    &__info {
      color: #407BFF;
      background: #e0e0e0;
      padding: 20px;
      text-transform: uppercase;
    }

     &__logo {
       width:60px;

       img {
         width: 100%;
       }
     }
   }
</style>
