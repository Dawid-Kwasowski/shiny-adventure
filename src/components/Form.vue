<template>
   <form
   class="form" 
   :action="computedEmail"
   enctype="multipart/form-data"
   method="POST"
   >
      <div class="form__wrapper">
         <div class="form__controls">
            <input class="form__input" type="text" placeholder="Wpisz swoje imię">
            <input class="form__input" type="email" placeholder="Wpisz swój email">
         </div>
         <div class="form__controls">
            <textarea class="form__textarea" name="" id="" cols="30" placeholder="Zapytanie Ofertowe" rows="10"></textarea>
         </div>
         <div class="form__controls">
            <input class="form__input form__input--submit" type="submit" value="Wyślij zapytanie">
         </div>
      </div>
   </form>
</template>

<script>
// import { computed } from '@vue/reactivity'
export default {
   data() {
      return {
         email: ':biuroprocleaningservice@gmail.com'
      }
   },
   computed: {
      computedEmail() {
         return `mailto:${this.email}`
      }
   }
}
</script>

<style lang="scss">
   .form {

      &__wrapper {
         display: flex;
         justify-content: center;
         flex-direction: column;
         margin: 0 5px;
         max-width: 600px;
         margin: auto;
      }

      &__controls {
         display: flex;
         flex-direction: column;
      }

      &__input {
         height: 40px;
         border: none;
         width: 100%;
         border-radius: 5px;
         margin: 5px 0;
         padding: 5px;
      }

      &__textarea {
         border-radius: 5px;
         padding: 5px;
         border: none;
      }
   }
</style>