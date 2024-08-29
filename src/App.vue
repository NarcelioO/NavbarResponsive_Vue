<script setup>
import Header from './components/ComponentHeader.vue';
import CardAlert from './components/CardAlert.vue'
import {ref} from 'vue'

const text = ref('Hello')


  function clicked()
  {
     console.log("Alo")
  }
  


</script>

<template>
  <div>
   
   
    <Header />
    <CardAlert variant="danger">
      {{ text }}
    </CardAlert @close="">
  </div>
  
</template>

<style scoped>
  
</style>
