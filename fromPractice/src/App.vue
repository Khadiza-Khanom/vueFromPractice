<script setup>
import{ref} from 'vue'
const checkValue= ref(true)
</script>

<template>
  <section class="mx-auto container">
    <h1 class="text-2xl mb-10">Vue Form</h1>
    <p class="mb-10"></p>
    <label for="">Display Random Image</label>
    <input class="ml-2" type="checkbox"  v-model="checkValue" />

    <img
    v-show="checkValue"
      class="mt-10 mx-auto w-[500px]"
      :src="`https://source.unsplash.com/random?version=${ Math.random()}`"
      alt=""  />
      
    <!-- <img
    v-if="checkValue"
      class="mt-10 mx-auto w-[500px]"
      :src="`https://source.unsplash.com/random?version=${ Math.random()}`"
      alt=""  /> -->

    

  </section>
</template>
<style scoped></style>