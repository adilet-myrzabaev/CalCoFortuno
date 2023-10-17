<template>
  <div class="px-3 md:px-9">
    <div class="box grid flex font-sans">
      <div class="col-12 lg:col-4 mb-4">
        <h1 class="text-6xl text-[#9771ff] font-bold uppercase text-center">biruni</h1>
        <p class="text-xl text-justify hidden lg:flex">Вы работаете над новым веб-приложением, которое предоставит пользователям удобный способ управления своими задачами и проектами. Вашей задачей является создание интуитивного интерфейса с удобным перетаскиванием задач и автоматизированным уведомлением пользователей о важных событиях. Также вам нужно обеспечить безопасное хранение данных и высокую производительность приложения, чтобы пользователи могли получать мгновенный доступ к своим задачам. Работая в команде разработчиков, вы будете использовать современные фреймворки и инструменты для достижения этой цели.</p>
      </div>
      <div class="col-12 lg:col-4 mb-4">
        <div class="flex flex-column justify-content-center align-items-center">
          <button class="btn btn-secondary bg-[#9771ff] border-none p-3" @click="changeRandom">Нажмите</button>
          <div class="line">
            <i class="pi pi-caret-down text-6xl"></i>
          </div>
          <div class="coleso-fortuno" :style="`transform: rotate(${randomRotateclass}deg)`">
            <div class="partent-coleso col1"></div>
            <div class="partent-coleso col2"></div>
            <div class="partent-coleso col3"></div>
            <div class="partent-coleso col4"></div>
            <div class="partent-coleso col5"></div>
            <div class="partent-coleso col6"></div>
            <div class="partent-coleso col7"></div>
          </div>
        </div>
      </div>
      <div class="col-12 lg:col-4 mb-4">
        <div class="content">
          <h1 class="text-center text-5xl text-[red] font-bold uppercase">Наказании</h1>
          <div class="flex align-items-center mb-4">
            <div class="w-2rem h-2rem mr-3 bg-[#2c3e50] rounded-[50%]"></div>
            <h5 class="m-0 leading-0">10круг бега без остановок</h5>
          </div>
          <div class="flex align-items-center mb-4">
            <div class="w-2rem h-2rem mr-3 bg-[violet] rounded-[50%]"></div>
            <h5 class="m-0 leading-0">Поднять стул стоя 15мин</h5>
          </div>
          <div class="flex align-items-center mb-4">
            <div class="w-2rem h-2rem mr-3 bg-[#00dc82] rounded-[50%]"></div>
            <h5 class="m-0 leading-6">Запрет на сидение</h5>
          </div>
          <div class="flex align-items-center mb-4">
            <div class="w-2rem h-2rem mr-3 bg-[gray] rounded-[50%]"></div>
            <div class="flex flex-column">
              <h5 class="m-0">Носит сумки всех в течение 2 часов (мальчики)</h5>
              <h5 class="m-0">Носит 3 сумки в течение 2 часов (девочки)</h5>
            </div>
          </div>
          <div class="flex align-items-center mb-4">
            <div class="w-2rem h-2rem mr-3 bg-[blue] rounded-[50%]"></div>
            <h5 class="m-0 leading-0">Уборка бируни</h5>
          </div>
          <div class="flex align-items-center mb-4">
            <div class="w-2rem h-2rem mr-3 bg-[orange] rounded-[50%]"></div>
            <h5 class="m-0 leading-6 w-8">Мальчики отжимания (40); Девочки присидания (50)</h5>
          </div>
          <div class="flex align-items-center mb-4">
            <div class="w-2rem h-2rem mr-3 bg-[pink] rounded-[50%]"></div>
            <h5 class="m-0 leading-0">До обеда не заходит в бируни</h5>
          </div>
          <div class="flex align-items-center mb-4">
            <div class="w-2rem h-2rem mr-3 bg-[red] rounded-[50%]"></div>
            <h5 class="m-0 leading-0">Счастливый билет</h5>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import {onMounted} from "vue";

let randomRotate = 0;
const randomRotateclass = ref(0);
const changeRandom = () =>  {
  while (true){
    randomRotate = Math.trunc(Math.random()*100000)
    if (randomRotate>=15000 && randomRotate <=30000){
      randomRotateclass.value = randomRotate
      return
    }
  }
}
changeRandom()
onMounted(() => {
  document.onkeypress = (event) => {

    if(event.charCode === 13){
      while (true){
        randomRotate = Math.trunc(Math.random()*100000)
        if (randomRotate>=15000 && randomRotate <=30000){
          randomRotateclass.value = randomRotate
          return
        }
      }
    }
  }
})
</script>

<style scoped>
.box{
  display: flex;
  justify-content: center;
  padding-top: 80px;
}
.partent-coleso{
  width: 150px;
  height: 150px;
  position: absolute;
  background: #2c3e50;
  transform:  skew(20deg,20deg);
  transform-origin: 100% 100%;
}
.col2{
  transform: rotate(50deg) skew(20deg,20deg);
  transform-origin: 100% 100%;
  background: violet;
}
.col3{
  transform: rotate(100deg) skew(20deg,20deg);
  transform-origin: 100% 100%;
  background: #00dc82;
}
.col4{
   transform: rotate(150deg) skew(20deg,20deg);
   transform-origin: 100% 100%;
   background: blue;
}
.col5{
    transform: rotate(200deg) skew(20deg,20deg);
    transform-origin: 100% 100%;
    background: rgb(128, 128, 128);
}
.col6{
  transform: rotate(250deg) skew(20deg,20deg);
  transform-origin: 100% 100%;
  background: orange;
}
.col7{
  transform: rotate(300deg) skew(20deg,20deg);
  transform-origin: 100% 100%;
  background: pink;
}
.coleso-fortuno{
  width: 300px;
  height: 300px;
  background-color: red;
  overflow: hidden;
  border-radius: 50%;
  transform-origin: 50% 50%;
  position: relative;
  transform: rotate(0deg);
  transition:all 10s cubic-bezier(0.53, 0, 0.58, 0.98)
}

</style>