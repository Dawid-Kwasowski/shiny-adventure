<template>
  <div class="wrapper">
    <section class="wrapper__navigation-panel navigation-panel">
      <div class="navigation-panel__logo">
        <img src="../src/assets/images/KOLOR.png" alt="logo">
      </div>
      <nav-bar></nav-bar>
    </section>
  </div>
</template>

<script>

import NavBar from "./components/NavBar.vue"
export default {
  name: 'App',
  components: {
    NavBar
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@500;600;700&display=swap');

  * {
    box-sizing: border-box;
    padding: 0;
    margin: 0;
  }
   .navigation-panel {
     font-family: 'Open Sans', sans-serif;
     background: #fff;
     display: flex;
     justify-content: space-between;
     align-content: center;
     width: 100%;
     min-height: 60px;
     padding: 6px 20px;
     &__logo {
       width:60px;

       img {
         width: 100%;
       }
     }
   }
</style>
