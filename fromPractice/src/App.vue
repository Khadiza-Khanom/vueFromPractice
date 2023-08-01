<script setup>
import {ref, reactive } from 'vue'
const saarcCountries = reactive([
  { name: "Bangladesh", capital: "Dhaka" },
  { name: "Nepal", capital: "Kathmandu" },
  { name: "Bhutan", capital: "Thimphu" },
  { name: "Sri Lanka", capital: "Colombo" },
  { name: "India", capital: "New Delhi" },
  { name: "Pakistan", capital: "Islamabad" },
  { name: "Maldives", capital: "Male" }
])

const capitals = ["Dhaka", "Kathmandu", "Thimphu", "Colombo", "New Delhi", "Islamabad", "Male"]
let score=ref(0)
let sh=ref(false)

const getScore=()=>{
sh.value=true
  saarcCountries.forEach(country=>{
    if(country.capital==country.answer){
    score.value++
    }
  
  })
 

 return score.value
  }

let cap=capitals.sort(()=>Math.random() - 0.5)


</script>

<template>
  <section class="mx-auto container text-left">
    <h1 class="text-2xl mb-10">Country Quiz</h1>
    <!-- <p class="mb-10">{{saarcCountries}}</p> -->
    <!-- <p>Your Score: {{ getScore() }}</p> -->
    <div class="my-5 border border-gray-400 p-5" v-for="country in saarcCountries">
      <p>What is the capital of {{country.name}}?</p>
    <template v-for="capital in cap">
      <input :name="country.name" type="radio" v-model="country.answer" :value="capital"/>
        <label class="ml-2 mr-2">{{capital}}</label>
    </template>
 
      
  
    </div>
    <button class="bg-red-400" @click="getScore()">Result</button>
    <p class="mb-10" v-show="sh">{{ score }}</p>
  </section>
</template>
<style scoped></style>