<template>
  <section :id="sectionID" class="intro">
 
     <div class="intro__img-container">
        <img src="../assets/images/introduction-image.svg" alt="">
     </div>
     
     <article class="intro__content">
        <header class="intro__header">
           <h3 >{{introDescriptionTitle}}</h3>
        </header>
        <p>{{introDescription}}</p>
     </article>
  </section>
</template>

<script>
export default {
   data() {
      return {
         introDescriptionTitle: 'Profesjonalne sprzątanie mieszkań, budynków i pomieszczeń',
         introDescription: 'PRO CLEANING SERVICE - jest firmą wykorzystującą atestowane i bezpieczne dla ludzi i zwierząt środki chemiczne. Pracujemy na nowoczesnym sprzęcie przemysłowym takich firm jak Prochem, Karcher.'
      }
   },
   props: {
      sectionID: String
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
      @media (min-width: 1024px) {
         flex-direction: row;
         width: 100%;
         &__img-container {
            width: 100%;
         }
      }
      img {
         @media (min-width:1024px) {
            width: 100%;
            flex-grow: 1;
         }
      }
      &__content {
         background:#fff;
         color: $dark-blue;
         font-size: 24px;
         font-weight: 500;
         text-align: center;
         padding: 30px 0;
         line-height: 1.5;
         @media (min-width: 1024px) {
            text-align: left;
            display: flex;
            flex-direction: column;
            justify-content: center;
            padding: 0 20px;
         }
      }
   }
</style>