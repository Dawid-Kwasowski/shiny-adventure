<template>
   <div class="slider">
      
      <div class="slider__wrapper">
         <div class="slider__controller">
         <div @click="prevImg" class="slider__controller-icon">
            <i class="fas fa-angle-left"></i>
         </div>
      </div>
        <div class="slider__content">
            <div class="slider__image">
               <template v-if="!images[currentImg].img">
                  <i class="far fa-images"></i>
               </template>
            </div>
            <div class="slider__description">
               <p>{{images[currentImg].description}}</p>
            </div>
        </div>
         <div @click="nextImg" class="slider__controller">
         <div class="slider__controller-icon">
            <i class="fas fa-angle-right"></i>
         </div>
      </div>
        <div class="slider__pagination">
           <div v-for="(image,index) in images" :key="index" class="slider__dot"></div>
        </div>
      </div>
      
   </div>
</template>

<script>
export default {
   data() {
      return {
         // temporary data 
         images: [
            {id: 1, img:null ,description: "Kompleksowe sprzątanie domu / mieszkania", alt: ""},
            {id: 2, img:null ,description: "Gruntowne lub poremontowe sprzątanie domu / mieszkania", alt: ""},
            {id: 3, img:null ,description: "Kompleksowe sprzątanie lokali po imprezach okolicznościowych", alt: ""},
            {id: 4, img:null ,description: "Mycie okien ", alt: ""},
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
}
</script>

<style lang="scss">
   .slider {
      display: flex;
      justify-content: center;
      align-content: center;
      width: 100%;
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
         height: 50%;
         width: 100%;
      }
      &__description {
         display: flex;
         justify-content: center;
         align-items: center;
         background: #263238;
         font-size: 24px;
         text-align: center;
         border-radius: 5px;
         min-height:50%;
         margin: 2px 0;
         width: 100%;
         padding: 10px;
         
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
      }
   }
</style>