<template>
  <div>
    <div class="main-wrapper">
       <div class="background-watermark">
      <img 
      src="@/assets/img/vue.jpeg" 
      alt="logo-vue" 
      width="500"
      v-if="visibilityImg"
      :class="filtersImage"
      :style="[opacityImage, sizeImage, rotateImage]"
      />
       </div>
      <div class="photo-parameters">
        <div class="visibility-wrapper">
          <h4>Видимость изображения:</h4>
          <button 
          class="show-button" 
          type="button"
          @click="visibilityImg = !visibilityImg"
          :class="visibilityImg ? '' : 'isActiveButton'"
          >Показать / Скрыть</button>
        </div>

        <h4>Фильтры:</h4>
        <div class="button-wrapper">
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.sepia = !filtersImage.sepia"
          :class='filtersImage.sepia ? "isActiveButton" : ""'
          >Сепия</button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.frame = !filtersImage.frame"
          :class="filtersImage.frame ? 'isActiveButton' : ''"
          >Рамка</button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.shadow = !filtersImage.shadow"
          :class="filtersImage.shadow ? 'isActiveButton' : ''"
          >Тень</button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.outline = !filtersImage.outline"
          :class="filtersImage.outline ? 'isActiveButton' : ''"
          >
            Обводка
          </button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.blur = !filtersImage.blur"
          :class="filtersImage.blur ? 'isActiveButton' : ''"
          >
            Размытие
          </button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.brightness = !filtersImage.brightness"
          :class="filtersImage.brightness ? 'isActiveButton' : ''"
          >
            Яркость
          </button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.saturate = !filtersImage.saturate"
          :class="filtersImage.saturate ? 'isActiveButton' : ''"
          >
            Насыщенность
          </button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.contrast =! filtersImage.contrast"
          :class="filtersImage.contrast ? 'isActiveButton' : ''"
          >
            Контраст
          </button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.grayscale = !filtersImage.grayscale"
          :class="filtersImage.grayscale ? 'isActiveButton' : ''"
          >
            Оттенок серого
          </button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.hueRotate = !filtersImage.hueRotate"
          :class="filtersImage.hueRotate ? 'isActiveButton' : ''"
          >
            Оттенок-поворот
          </button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.invert = !filtersImage.invert"
          :class="filtersImage.invert ? 'isActiveButton' : ''"
          >
            Инвертировать
          </button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.outset = !filtersImage.outset"
          :class="filtersImage.outset ? 'isActiveButton' : ''"
          >
            Обводка с градиентом
          </button>
        </div>
      </div>
    </div>
    <div class="input-wrapper">
      <p>{{ `Текущая прозрачность: ${opacityImg.currentOpacity}%` }}</p>
      <input 
      type="range" 
      :value="opacityImg.currentOpacity"
      @input="opacityImg.currentOpacity = $event.target.value"
      :min="opacityImg.opacityMin"
      :max="opacityImg.opacityMax"
      />

      <p>{{ `Текущая высота: ${sizeImg.currentHeight}px` }}</p>

      <input 
      type="range" 
      :value="sizeImg.currentHeight"
      @input="sizeImg.currentHeight = $event.target.value"
      :min="sizeImg.minHeight"
      :max="sizeImg.maxHeight"
      />

      <p>{{ `Текущая ширина: ${sizeImg.currentWidth}px` }}</p>

      <input 
      type="range" 
      :value="sizeImg.currentWidth"
      @input="sizeImg.currentWidth = $event.target.value"
      :min="sizeImg.minWidth"
      :max="sizeImg.maxWidth"
      />

      <p>{{ `Текущий угол поворота: ${rotateImg.currentRotate} deg` }}</p>
      <input 
      type="range" 
      :value="rotateImg.currentRotate"
      @input="rotateImg.currentRotate = $event.target.value"
      :min="rotateImg.rotateMin"
      :max="rotateImg.rotateMax"
      />
    </div>
  </div>
</template>

<script>
export default {
   name: 'PhotoProcessing',
   data() {
      return {
         visibilityImg: true,
         filtersImage: {
            sepia: false,
            frame: false,
            shadow: false,
            outline: false,
            blur: false,
            brightness: false,
            contrast: false,
            saturate: false,
            grayscale: false,
            hueRotate: false,
            invert: false,
            outset: false,
         },
         isActiveButton: false,
         opacityImg: {
            opacityMax: 100,
            opacityMin: 0,
            currentOpacity: 100
         },
         sizeImg: {
            minHeight: 1,
            maxHeight: 110,
            currentHeight: 100,
            minWidth: 1,
            maxWidth: 105,
            currentWidth: 100,
         },
         rotateImg: {
            rotateMin: -180,
            rotateMax: 180,
            currentRotate: 0,
         }
      }
   },
   computed: {
      opacityImage() {
         return {
            opacity: `${this.opacityImg.currentOpacity}%`
         }
      },
      sizeImage() {
         return {
            height: `${this.sizeImg.currentHeight}%`,
            width: `${this.sizeImg.currentWidth}%`
         }
      },
      rotateImage() {
         return {
            transform: `rotate(${this.rotateImg.currentRotate}deg)`
         }
      }
   }
};
</script>

<style lang="scss" scoped>
.main-wrapper {
  display: flex;
  align-items: center;
}
.photo-parameters {
  margin-left: 25px;
  &__button {
    width: 48%;
    cursor: pointer;
    padding: 5px 10px;
    border: 1px solid black;
    transition: 0.2s ease-in;
    margin: 0 5px 5px 0;
  }
  &__button:hover {
    background-color: rgb(250, 173, 73);
  }
}
.button-wrapper {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  width: 400px;
}
h4 {
  margin: 10px 0;
}
input[type="range"] {
  width: 500px;
}
.input-wrapper {
  margin-top: 25px;
}
.visibility-wrapper{
   margin-bottom: 25px;
}
.show-button{
   cursor: pointer;
   padding: 5px 10px;
   border: 1px solid black;
   transition: 0.2s ease-in;
}
.show-button:hover{
   background-color: rgb(250, 173, 73);
}
.background-watermark{
   background-color: rgba(172, 171, 170, 0.747);
   width: 500px;
   height: 298px;
}
.sepia{
   filter: sepia(100%);
}
.frame{
   border: 3px dashed rgb(141, 0, 0);
}
.shadow{
   box-shadow: 0 0 10px rgba(0,0,0,0.5);;
}
.outline{
      border: 3px solid black;
}
.blur{
   filter: blur(3px);
}
.brightness{
   filter: brightness(40%);
}
.contrast {
   filter: contrast(15%);
}
.grayscale{
   filter: grayscale(.75);
}
.saturate{
   filter: saturate(350%);
}
.hueRotate{
   filter: hue-rotate(270deg);
}
.invert{
   filter: invert(100%);
}
.outset{
   border: 5px outset rgb(174, 0, 255);
}
.isActiveButton{
   background-color: rgb(250, 173, 73);
}
</style>