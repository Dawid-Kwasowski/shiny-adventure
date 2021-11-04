<template>
  <section class="intro">
     <div class="intro__img-container">
        <img src="../assets/images/introduction-image.svg" alt="">
     </div>
     <article class="intro__content">
        <header class="intro__header">
           <h3 >{{introDescription}}</h3>
        </header>
     </article>
  </section>
</template>

<script>
export default {
   data() {
      return {
         introDescription: 'Profesjonalne sprzątanie mieszkań, budynków i pomieszczeń'
      }
   }
}
</script>

<style lang="scss">
   $dark-blue: #455A64;
   .intro {
      font-family: 'Open Sans', sans-serif;
      width: 100%;
      display: flex;
      flex-direction: column;
      img {
         @media (min-width:1024px) {
            width: 50%;
         }
      }
      &__content {
         background: $dark-blue;
         color: #fff;
         font-size: 24px;
         font-weight: 500;
         text-align: center;
         padding: 30px 0;
      }
   }
</style>