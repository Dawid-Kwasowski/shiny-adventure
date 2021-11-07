<template>
  <section class="locations">
     <div class="locations__wrapper">

         <div class="locations__header">
            <div class="locations__header-icon">
               <i class="fas fa-map-marker-alt"></i>
            </div>
            <header class="locations__header-title">
               <h3>{{title}}</h3>   
            </header>
        </div>

        <div class="locations__content">
           <span class="location__item">SOPOT</span>|
           <span class="location__item">GDAŃSK</span>|
           <span class="location__item">GDYNIA</span>
        </div>

     </div>
  </section>
</template>

<script>
export default {
   data() {
      return {
         title: 'Lokalizacja'
      }
   }
}
</script>

<style lang="scss">
   .locations {
      
      &__wrapper {
         display: flex;
         flex-direction: column;
         align-items: center;
         justify-content: space-between;
         padding: 30px;
         widows: 100%;
         min-height: 150px;
      }

      &__header {
         position: relative;
         text-align: center;
         color: #455A64;
      }

      &__header-icon {
         position: absolute;
         z-index: 1;
         left: 50%;
         top: -50%;
         transform: translateX(-50%);
         font-size: 60px;
         color: #E0E0E0;
      }

      &__header-title {
         position: relative;
         z-index: 2;
         font-size: 24px;
      }

      &__content {
         margin: 20px 0;
         position: relative;
         z-index: 2;
         font-size: 24px;
         display: flex;
         align-items: center;
         justify-content: space-evenly;
         width: 100%;
      }
   }
      
</style>