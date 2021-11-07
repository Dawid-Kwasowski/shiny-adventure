<template>
  <section :id="sectionID" class="web-section">
     <div :class="[darkMode ? 'web-section__wrapper--dark-mode':'','web-section__wrapper']">
         <div class="web-section__header-wrapper">
           <header :class="[darkMode ? 'web-section__header--dark-mode':'','web-section__header']">
            <slot name="header"></slot>
           </header>
         </div>
         <div :class="[darkMode ? 'web-section__body':'','web-section__body']">
            <slot name="body"></slot>
         </div>
         <div class="web-section__footer">
            <slot name="footer"></slot>
         </div>
     </div>
  </section>
</template>

<script>
export default {
   props: {
      darkMode: Boolean,
      sectionID: String,
   }
}
</script>

<style lang="scss">
   $dark-blue: #455A64;
   .web-section {
      
      &__wrapper {
         padding: 10px 20px;
         display: flex;
         flex-direction: column;
         align-items: center;

         &--dark-mode {
            color: #fff;
            background: $dark-blue;
         }
      }

      &__header {
         text-align: center;
         text-transform: uppercase;
         font-size: 32px;
         font-weight: 500;
         color: $dark-blue;
         border-bottom: 1px solid $dark-blue;
         margin: 20px 0;
         // width: 200px;
         &--dark-mode {
            color: #fff;
            border-bottom: 1px solid #fff;
         }
      }

      &__body {
         padding: 10px;
      }
   }
</style>