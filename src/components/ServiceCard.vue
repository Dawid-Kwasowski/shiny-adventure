<template>
  <div class="card">
     <div class="card__wrapper">
        <div class="card__icon">
           <slot name="icon"></slot>
        </div>
        <div class="card__service-title">
           <slot name="title"></slot>
        </div>
     </div>
  </div>
</template>

<script>
export default {
   
}
</script>

<style lang="scss">
   .card {
      width: 250px;
      height: 300px;
      background: #fff;
      padding: 30px;
      margin: 10px;
      display: flex;
      border-radius: 5px;
      box-shadow: 0 6px 10px 4px #eee;
      justify-content: center;
      position: relative;
      &__wrapper {
         display: flex;
         flex-direction: column;
         justify-content: space-evenly;
         align-items: center;
      }
      &__icon {
         background: #407BFF;
         border-radius: 100%;
         width: 60px;
         height: 60px;
         font-size: 24px;
         display: flex;
         justify-content: center;
         align-items: center;
         color: #fff;
      }
      &__service-title {
         color: #455A64;
         margin: 10px;
         text-align: center;

      }
   }
</style>