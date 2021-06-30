<template>
  <div>
    <div class="main-wrapper">
      <img src="@/assets/img/vue.jpeg" alt="logo-vue" width="500" />
      <div class="photo-parameters">
        <div class="visibility-wrapper">
          <h4>Видимость изображения:</h4>
          <button class="show-button" type="button">Показать / Скрыть</button>
        </div>

        <h4>Фильтры:</h4>
        <div class="button-wrapper">
          <button class="photo-parameters__button" type="button">Сепия</button>
          <button class="photo-parameters__button" type="button">Рамка</button>
          <button class="photo-parameters__button" type="button">Тень</button>
          <button class="photo-parameters__button" type="button">
            Обводка
          </button>
          <button class="photo-parameters__button" type="button">
            Размытие
          </button>
          <button class="photo-parameters__button" type="button">
            Яркость
          </button>
          <button class="photo-parameters__button" type="button">
            Яркость
          </button>
          <button class="photo-parameters__button" type="button">
            Контраст
          </button>
          <button class="photo-parameters__button" type="button">
            Оттенок серого
          </button>
          <button class="photo-parameters__button" type="button">
            Оттенок-поворот
          </button>
          <button class="photo-parameters__button" type="button">
            Инвертировать
          </button>
          <button class="photo-parameters__button" type="button">
            Постеризовать
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
export default {};
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
</style>