<template>
  <div class="service-list">
     <ul class="service-list__wrapper">
        <li v-for="(service,index) in serviceList" :key="index" class="service-list__item">
           <span class="service__text service__text--service-meters">{{service.meters}}</span>
           <span v-if="service.info" class="service__text service__text--info">{{service.info}}</span> 
           <span class="service__text service__text--service-price">{{service.price}}</span>
        </li>
     </ul>
  </div>
</template>

<script>
export default {
   props: {
      serviceList: Array
   },
}
</script>

<style lang="scss">
   .service-list {
      width: 100%;
      display: flex;
      justify-content: center;
      margin: 10px 0;
      border: 2px solid #455a64;
      padding: 10px;
      &__wrapper {
         list-style: none;
         width: 100%;
      }

      &__item {
         font-size: 24px;
         display: flex;
         justify-content: space-between;
         border-bottom: 2px solid #455a64;
         color: #455A64;

         &:last-child {
            border-bottom: none;
         }
      }
   }
</style>