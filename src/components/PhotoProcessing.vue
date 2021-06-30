<template>
  <div>
    <div class="main-wrapper">
       <div class="background-watermark">
      <img 
      src="@/assets/img/vue.jpeg" 
      alt="logo-vue" 
      width="500"
      v-if="visibilityImg"
      :class='filtersImage'
      />
       </div>
      <div class="photo-parameters">
        <div class="visibility-wrapper">
          <h4>Видимость изображения:</h4>
          <button 
          class="show-button" 
          type="button"
          @click="visibilityImg = !visibilityImg"
          >Показать / Скрыть</button>
        </div>

        <h4>Фильтры:</h4>
        <div class="button-wrapper">
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.sepia = !filtersImage.sepia"
          >Сепия</button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.frame = !filtersImage.frame"
          >Рамка</button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.shadow = !filtersImage.shadow"
          >Тень</button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.outline = !filtersImage.outline"
          >
            Обводка
          </button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.blur = !filtersImage.blur"
          >
            Размытие
          </button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.brightness = !filtersImage.brightness"
          >
            Яркость
          </button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.saturate = !filtersImage.saturate"
          >
            Насыщенность
          </button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.contrast =! filtersImage.contrast"
          >
            Контраст
          </button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.grayscale = !filtersImage.grayscale"
          >
            Оттенок серого
          </button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.hueRotate = !filtersImage.hueRotate"
          >
            Оттенок-поворот
          </button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.invert = !filtersImage.invert"
          >
            Инвертировать
          </button>
          <button 
          class="photo-parameters__button" 
          type="button"
          @click="filtersImage.outset = !filtersImage.outset"
          >
            Обводка с градиентом
          </button>
        </div>
      </div>
    </div>
    <div class="input-wrapper">
      <h4>Прозрачность:</h4>
      <input type="range" />

      <h4>Размер:</h4>
      <input type="range" />

      <h4>Поворот:</h4>
      <input type="range" />
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
         isActiveButton: false
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
</style>