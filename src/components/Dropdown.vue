<template>
  <div class="dropdown">
     <div class="dropdown__wrapper">
        <div @click="toggleDropdown" class="dropdown__btn">
           <span class="dropdown__btn-text">{{currentService}}</span>
           <span class="dropdown__btn-icon" v-show="!isActive">
              <i class="fas fa-angle-down"></i>
           </span>
           <span class="dropdown__btn-icon" v-show="isActive">
              <i class="fas fa-angle-up"></i>
           </span>
        </div>
        <div v-show="isActive" class="dropdown__service-list">
           <ul class="dropdown__service-list-wrapper">
              <li 
              v-for="(service,index) in services" 
              :key="index"
              @click="selectService(service)" 
              class="dropdown__service-item">
               {{service.title}}
              </li>
           </ul>
        </div>
     </div>
  </div>
</template>

<script>
export default {
   data() {
      return {
         isActive: false,
         currentService: 'Wybierz usługę',
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
         ]
      }
   },
   methods: {
      // method which toggle a dropdown
      toggleDropdown() {
         return this.isActive = !this.isActive
      },
      // emit event which ill be sending a paylod
      selectService(serviceItem) {
         this.currentService = serviceItem.title
         return this.$emit('selectList',serviceItem.priceList)
      } 
   }
}
</script>

<style lang="scss">
   .dropdown {
      width: 100%;
      display: flex;
      justify-content: center;
      position: relative;
      &__wrapper {
         width: 300px;
      }

      // dropdown btn below
      &__btn {
         height: 60px;
         background: #455A64;
         border-radius: 5px;
         padding: 18px 25px;
         display: flex;
         justify-content: space-between;
         align-items: center;
         cursor: pointer;
         
      }
      &__btn-text {
         font-size: 18px;
         font-weight: 700;
         color: #fff;
         overflow: hidden;
         white-space: nowrap;
         text-overflow: ellipsis;

         height: 100%;
      }
      &__btn-icon {
         color: #fff;
         font-size: 30px;
      }

      // service list below
      &__service-list {
         background: #e0e0e0;
         border-radius: 5px;
         margin: 5px 0;
         height: 190px;
         overflow-y: scroll;
      }

      &__service-list-wrapper {
         list-style: none;
         padding: 5px;
      }

      &__service-item {
         color:#455A64;
         font-size: 18px;
         font-weight: 500;
         margin: 8px;
         text-align: center;
         cursor: pointer;
         border-bottom: 1px solid #455A64;
         padding: 5px 0;
      }
   }
   
</style>