<template>
   <teleport to="#modals">
      <div v-if="isActive" @click.self="closeModal" class="modal-backdrop"></div>
         <div v-if="isActive" class="modal">
         <div class="modal__wrapper">
            <div class="modal__header">
               <slot name="header"></slot>
               <button class="modal__close-btn" @click="closeModal">
                  <i class="fas fa-times"></i>
               </button>
            </div>
            <div class="modal__body">
               <slot name="body"></slot>
            </div>
            <div class="modal__footer">
               <slot name="footer"></slot>
            </div>
         </div>
      </div> 
   </teleport>
</template>

<script>
export default {
   props: {
      isActive: Boolean,
   },
   data() {
      return {
         isModalActive: this.isActive
      }
   },
   methods: {
      closeModal() {
        return this.$emit('closeModal')
      }
   }
}
</script>

<style lang="scss">
   $dark-color: #263238;
   .modal-backdrop {
      background: $dark-color;
      opacity: .8;
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
   }

   .modal {
      position: fixed;
      top: 30%;
      left: 50%;
      transform: translate(-50%,-50%);
      &__wrapper {
         box-shadow: 0px 0px 6px 1px $dark-color;
         border-radius: 5px;
         display: flex;
         flex-direction: column;
         justify-content: space-around;
         align-items: center;
         background: #fff;
         min-width: 300px;
         min-height: 200px;
         padding: 10px 30px;
      }

      &__header {
         border-bottom: 1px solid $dark-color;
         width: 100%;
         display: flex;
         align-items: center;
         justify-content: space-between;
         text-transform: uppercase;
      }
      &__body {
         width: 100%;
         text-align: center;
      }

      &__close-btn {
         width: 40px;
         height: 40px;
         border-radius: 100%;
         outline: none;
         border: none;
         font-size: 18px;
         background: transparent;
      }
   }

</style>