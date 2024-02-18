<script setup>
import { ref } from 'vue';
 let res =ref([])
const api = 'https://jsonplaceholder.typicode.com/users'
fetch(api)
.then(response=>{
  if(!response.ok){
    throw new Error('Network problem');
  }
  return response.json()
})
.then(data=>{
 res.value = data
  console.log(data)
  return res.value
})
.catch(error=>{
  console.error(error)
})


</script>

<template>
<p class="text-red-500" v-for="ress,index in res" :key="index">{{ ress.id }} --- {{ress.name }}</p>


</template>

<style scoped>
</style>
