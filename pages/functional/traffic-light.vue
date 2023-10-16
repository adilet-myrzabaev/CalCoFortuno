<template>
  <div>
    <div class="box">
      <div  :class="{ circle: true, 'red': light === 'red'}"></div>
      <div  :class="{ circle: true, 'yellow': light === 'yellow' }" style="color: white; font-size: 18px; display: flex; justify-content: center; align-items: center; ">{{getcount}}</div>
      <div  :class="{ circle: true, 'green': light === 'green' }" ></div>
    </div>
  </div>
</template>

<script setup lang="ts">
let light = ref('red')
let count = 10
let getcount = ref(count)
const selectLight = () => {
  if (light.value === 'red') {
    light.value = 'yellow'
    getcount.value = count
  } else if (light.value === 'yellow') {
    light.value = 'green'
    getcount.value = count
  }
  else if (light.value === 'green') {
    light.value = 'red'
    getcount.value = count
  }
}
setInterval(selectLight, getcount.value*1000)

// Вывод на экран секунды
setInterval(() => {
  if (light.value === 'red') {
    getcount.value--;
  }
  else if (light.value === 'yellow') {
    getcount.value--;
  }
  else if (light.value === 'green') {
    getcount.value--;
  }
}, 1000);
</script>
<style scoped>
.box{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
  height: 250px;
  width: 80px;
  padding: 20px 0;
  border-radius: 50px;
  background-color: #2c3e50;
}
.circle{
  position: relative;
  height: 45px;
  width: 45px;
  border-radius: 100%;
  background-color: rgb(128, 128, 128);
}
.circle.red{
  background: #ff3822;
  box-shadow: 0 0 60px 10px #ff3822;
}
.circle.yellow{
  background: #eeff03;
  box-shadow: 0 0 60px 10px #eeff03;
}
.circle.green{
  background: #06ff59;
  box-shadow: 0 0 60px 10px #06ff59;
}
</style>