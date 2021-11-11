<template>

   <div @click="openModal" class="fab fab--blue">
      <div class="fab__icon">
         <i class="fas fa-phone"></i>
      </div>

      <modal @closeModal="isActive = !isActive" :isActive="isActive">
         <template #header>
            <h3>Zadzwoń do Nas</h3>
         </template>
         <template #body>
            <h3>NR TEL: +48 790 848 040</h3>
         </template>
      </modal>
   </div>
</template>
<script>
import Modal from "./Modal.vue"
export default {
   data() {
      return {
         isActive: false
      }
   },
   components: {
      Modal,
   },
   methods: {
      openModal() {
         return this.isActive = !this.isActive
      }
   }

}
</script>
<style lang="scss" scoped>
   .fab {
      cursor: pointer;
      position: fixed;
      bottom: 30px;
      right: 20px;
      width: 70px;
      height: 70px;
      font-size: 30px;
      border-radius: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
      box-shadow: 0px 0px 8px 1px #263238;
      z-index: 999;
      &__icon {
         display: flex;
         align-items: center;
         justify-content: center;
      }

      &--blue {
         background: #407BFF;
         color: #fff;
      }
   }
</style>