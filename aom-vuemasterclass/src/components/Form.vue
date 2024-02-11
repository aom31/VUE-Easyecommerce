<template>
    <div>
      <div> {{ fullname }}</div>
     
      <input type="text" v-model="formDataName.firstname">
      <input type="text" v-model="formDataName.lastname">
    </div>
</template>
  
<script setup lang='ts'>
import { reactive, ref, watch, watchEffect } from 'vue';

  const fullname = ref('')
  const formDataName = reactive({
    firstname:'',
    lastname:'',
  })
  


  watchEffect( () =>{
   fullname.value = formDataName.firstname + formDataName.lastname
  })
</script>
  
<style>
  
</style>