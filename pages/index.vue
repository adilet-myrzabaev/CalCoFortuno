<script setup lang='ts'>
import {router} from "@histoire/app/src/app/router";

const result = ref('')
const reset = () => {
  result.value = ''
}
const numbers = ref([
    1,2,3,4,5,6,7,8,9,0,"00"
])
const operations = ref([
  "/","*","-","+",
])
const input = (char: any) => {
  result.value += char
}
const deleted = () =>{
  result.value =result.value.slice(0,-1)
}
const calc = () => {
result.value = eval(result.value)
}

</script>

<template>
  <div class="container">
    <button @click="router.push('/functional/coleso_fortuna')">Coleso-Fortun</button>
    <div class="w-[300px] h-full bg-gray-400 m-auto p-5 mt-8 border-round-md">
      <div class="bg-white border-round-md">
        <input
            class="w-full text-end text-2xl px-3 py-2 border-none border-round-md"
            v-model.number="result"
            placeholder="0"
        >
      </div>
      <div class="grid mt-5">
        <div class="col-9">
          <div class="grid justify-center">
            <div class="col-4">
              <Button @click="reset()" class="integers">AC</Button>
            </div>
            <div class="col-4">
              <Button @click="deleted" class="integers">DE</Button>
            </div>
            <div class="col-4">
              <Button @click="input('.')" class="integers">.</Button>
            </div>
            <div v-for="num in numbers" class="col-4">
              <Button @click="input(num)" class="integers">{{num}}</Button>
            </div>
          </div>
        </div>
        <div class="col-3">
          <div class="grid">
            <div v-for="op in operations" class="col-12">
              <Button @click="input(op)" class="integers integers--gray hover:bg-orange-300">{{op}}</Button>
            </div>
            <div class="col-12">
              <Button @click="calc()" class="integers integers--gray hover:bg-orange-300 border-round-sm text-5xl">=</Button>
            </div>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>
