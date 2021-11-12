<template>
   
   <nav class="nav">
      <div @click="toggleBurger" class="hamburger-menu" v-show="!isDesktop">
         <div class="hamburger-menu__line hamburger-menu__line--top"></div>
         <div class="hamburger-menu__line hamburger-menu__line--middle"></div>
         <div class="hamburger-menu__line hamburger-menu__line--bottom"></div>
      </div>
      <ul v-if="isDesktop" :class="[isActive ? 'nav__item-list--active': '', 'nav__item-list']">
         <li v-for="(item, index) in itemList" class="nav__item" :key="index">
            <a class="nav__item-link" :href="item.anchor">{{item.title}}</a>
         </li>
      </ul>
      <ul v-else :class="[isActive ? 'nav__item-list--active': '', 'nav__item-list']">
         <li v-for="(item, index) in itemList" class="nav__item" :key="index">
            <a class="nav__item-link" :href="item.anchor">{{item.title}}</a>
         </li>
      </ul>
   </nav>
</template>

<script>
export default {
   data() {
      return {
         itemList : [
            {title: "O nas", anchor: ""},
            {title: "Usługi", anchor: ""},
            {title: "Cennik", anchor: ""},
            {title: "Kontakt", anchor: ""}
         ],
         isDesktop: matchMedia("(min-width:1024px)").matches,
         isActive: this.isDesktop ? true : false         
      }
   },
   methods: {
      toggleBurger() {
         return this.isDesktop ? null : (this.isActive = !this.isActive)
      }
   }
}
</script>

<style lang="scss">  
   $nav-color: #407BFF;
   $dark-color: #263238;
   // Mobile First

   .hamburger-menu {
      width: 30px;
      height: 30px;
      display: flex;
      align-items: flex-end;
      flex-direction: column;
      
      &__line {
         height: 3px;
         width: 30px;
         margin: 2.5px;
         background: $dark-color;
         border-radius: 5px;

         &--middle {
            width: 25px;
         }
      }

   }

   .nav {
      display: flex;
      align-items: center;
      z-index: 9999;
      &__item-list {
         position: fixed;
         display: none;
         list-style: none;
         justify-content: space-evenly;
         flex-direction: column;
         background: #fff;
         @media (min-width: 1024px) {
            display: flex;
            position: static;
            flex-direction: row;
            transform: translate(0,0);
         }

         &--active {
            display: flex;
            top: 12%;
            left: 0;
            right: 0;
            bottom: 0;
         }
      }

      &__item {
         margin: 5px;
         padding: 5px;
         text-align: center;
         &:hover {
            text-decoration: underline;
         }
      }

      &__item-link {
         text-decoration: none;
         color: $nav-color;
         text-transform: uppercase;
          font-size: 48px;
        @media (min-width: 1024px) {
            font-size: 24px;
        }
      }
   }
</style>