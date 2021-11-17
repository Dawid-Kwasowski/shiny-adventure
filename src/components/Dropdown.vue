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
      }
   },
   props: {
      services: []
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