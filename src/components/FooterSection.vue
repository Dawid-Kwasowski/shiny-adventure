<template>
  <footer class="footer">
     <div class="footer__wrapper">
        <article class="footer__socials">
           <header class="footer__header">
            <h4>Śledź nas:</h4>   
           </header>
           <section class="footer__social-links">
               <a :href="instagram">
                  <i class="fab fa-instagram-square"></i>
                  <span> na instagramie</span>
               </a>
               <a :href="facebook">
                  <i class="fab fa-facebook-square"></i>
                  <span> na facebooku</span>
               </a>
               <a :href="developedBy">
                  <i class="fas fa-terminal"></i>
                  <span> by Dawid-Kwasowski</span>
               </a>
           </section>
        </article>
     </div>
  </footer>
</template>

<script>
export default {
   data() {
      return {
         facebook: 'https://www.facebook.com/PProcleaningservice',
         insagram: 'https://www.instagram.com/_pro_cleaning_service/',
         hashtags: ['trójmiasto'],
         developedBy: 'https://dawid-kwasowski.github.io/portfolio/'
      }
   }
}
</script>

<style lang="scss">
   .footer {
      position: relative;
      width: 100%;
      &__wrapper {
         color: #fff;
         font-size: 24px;
         background: #263238;
         padding: 10px 20px;

      }
      &__social-links {
                  font-size: 24px;
         display: flex;
         flex-direction: column;

         a {
            color: #455A64;
            text-decoration: #e0e0e0;
         }
      }
   }
</style>