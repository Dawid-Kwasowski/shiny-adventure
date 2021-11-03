<template>
   <nav class="nav">

      <ul class="nav__item-list" v-show="isDesktop">
         <li v-for="(item, index) in itemList" class="nav__item" :key="index">
            <a class="nav__item-link" href="{{item.anchor}}">{{item.title}}</a>
         </li>
      </ul>
   </nav>
</template>

<script>
export default {
   data() {
      return {
         itemList : [
            {title: "O nas", anchor: "#"},
            {title: "Usługi", anchor: "#"},
            {title: "Cennik", anchor: "#"},
            {title: "Kontakt", anchor: "#"}
         ],
         isDesktop: matchMedia("(min-width:1024px)").matches         
      }
   }
}
</script>

<style lang="scss">  
   $nav-color: #407BFF;
   // Mobile First
   .nav {
      display: flex;
      align-items: center;
      &__item-list {
         display: flex;
         list-style: none;
         justify-content: space-evenly;
         
      }

      &__item {
         margin: 5px;
         padding: 5px;
         &:hover {
            text-decoration: underline;
         }
      }

      &__item-link {
         text-decoration: none;
         color: $nav-color;
         text-transform: uppercase;
         font-size: 24px;
      }
   }
</style>