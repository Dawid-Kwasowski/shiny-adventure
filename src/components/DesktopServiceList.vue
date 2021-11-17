<template>
  <div class="service-list">
        <ul class="service-list__wrapper">
           <div class="service-list__titles">
               <h1>Tytuł usługi</h1>
               <h1>Cena</h1>
            </div>
           <li class="service-list__item" v-for="(service,index) in services" :key="index">
              <div class="service-list__item-title">{{service.title}}</div>
              <div class="service-list__subitem" v-for="(price,index) in service.priceList" :key="index">
                 <span class="service-list__subitem-info" v-if="price.info">{{price.info}}</span>
                 <div class="service-list__price-section" else>
                    <div class="service-list__subitem-meters">{{price.meters}}</div>
                    <div class="service-list__subitem-price">{{price.price}}</div>
                 </div>
              </div>
           </li>
        </ul>
  </div>
</template>

<script>
export default {
   props: {
      services: Array
   }
}
</script>

<style lang="scss">

   .service-list {
      display: flex;
      justify-content: space-between;
      &__item-title {
         width: 40%;
      }
      &__subitem {
         display: flex;
         text-align: center;
         flex-direction: column;
         justify-content: center;
      }

      &__titles {
         display: flex;
         width:100%;
         justify-content: space-between;
         color: #455A64;
         margin-bottom: 10px;
      }
      &__subitem-info {
         font-weight: bolder;
      }

      &__subitem-meters {
         font-weight: bolder;
      }
   }
   
</style>