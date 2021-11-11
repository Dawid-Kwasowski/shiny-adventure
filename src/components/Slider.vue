<template>
   <div class="slider">
      
      <div class="slider__wrapper">
         <div class="slider__controller slider__controller--left">
            <div @click="prevImg" class="slider__controller-icon">
               <i class="fas fa-angle-left"></i>
            </div>
         </div>
        <div class="slider__content">
            <div class="slider__image">
               <template v-if="!images[currentImg].img">
                  <i class="far fa-images"></i>
               </template>
               <template v-else>
                  <img :src="images[currentImg].img" alt="">
               </template>
            </div>
            <div class="slider__description">
               <p>{{images[currentImg].description}}</p>
            </div>
        </div>
         <div @click="nextImg" class="slider__controller slider__controller--right">
            <div class="slider__controller-icon">
               <i class="fas fa-angle-right"></i>
            </div>
         </div>
      </div>
      
   </div>
</template>

<script>
import imageCat from '../assets/images/cat-sm.jpg'
import imageCar from '../assets/images/car-sm.jpg'
import imageRoom from '../assets/images/room-sm.jpg'
import imageVacuumCleaner from '../assets/images/vacuum-cleaner-sm.jpg'
export default {
   data() {
      return {
         // temporary data 
         images: [
            {id: 1, img: imageCat ,description: "Bezpieczne dla zwierząt", alt: ""},
            {id: 2, img: imageCar ,description: "Kompleksowe sprzątanie i mycie aut", alt: ""},
            {id: 3, img: imageRoom ,description: "Kompleksowe sprzątanie lokali po imprezach okolicznościowych", alt: ""},
            {id: 4, img: imageVacuumCleaner ,description: "Odkurzanie i pranie dywanów ", alt: ""},
         ],
         currentImg: 0
      }
   },
   methods: {
     nextImg() {
        if(this.currentImg === this.images.length) {
           return this.currentImg = 0
        }
        return this.currentImg += 1
     },
     prevImg() {
        if(this.currentImg === 0) {
           return this.currentImg = this.images.length
        }
        return this.currentImg -= 1
     }
   },
   mounted() {
      setInterval(() => {
         if(this.currentImg === this.images.length) {
           return this.currentImg = 0
        }
        return this.currentImg += 1
      },3000) 
   }
}
</script>

<style lang="scss">
   .slider {
      display: flex;
      justify-content: center;
      align-content: center;
      width: 100%;
      position: relative;
      &__wrapper {
         display: flex;
         justify-content: center;
         width: 100%;
      }
      &__image {
         background: #e0e0e0;
         font-size: 64px;
         display: flex;
         justify-content: center;
         align-items: center;
         border-radius: 5px;
         margin: 5px 0;
         height: 100%;
         width: 100%;
         img {
            border-radius: 5px;
            width: 100%;
            height: 100%;
         }
      }
      &__description {
         display: flex;
         justify-content: center;
         align-items: center;
         background: #263238;
         font-size: 24px;
         text-align: center;
         border-radius: 0px 0 5px 5px;
         opacity: .8;
         width: 100%;
         padding: 10px;
         position: absolute;
         bottom: 0px;
         p {
            width: 100%;
            overflow-wrap: break-word;
         }
      }
      &__content {
         display: flex;
         flex-direction: column;
         align-items: center;justify-content: center;
         border-radius: 5px;
         height: 500px;
         width: 100%;
      }
      &__controller {
         font-size: 64px;
         margin: 0 5px;
         display: flex;
         align-items: center;
         position: absolute;

         &--left {
            top: 50%;
            left: 10px;
            transform: translateY(-50%);
         }
         &--right {
            top: 50%;
            right: 10px;
            transform: translateY(-50%);
         }
      }
   }
</style>