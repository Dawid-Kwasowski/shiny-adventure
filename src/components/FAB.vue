<template>
   <div @click="openModal" class="fab fab--blue">
      <div class="fab__icon">
         <i class="fas fa-phone"></i>
      </div>
   </div>
</template>
<script>
export default {
   methods: {
      openModal() {
         return alert('TEST')
      }
   }
}
</script>
<style lang="scss">
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