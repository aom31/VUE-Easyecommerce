<template>
  <div>
    <input type="text" v-model="message">
  </div>
  <CounterComponent :messageTextFromProp="message" :changeMessageText="changeMessageText"></CounterComponent>
  
</template>

<script setup lang="ts">
import FormComponent from "./components/Form.vue";
import CounterComponent from "./components/Counter.vue";
import { ref } from "vue";


const message = ref('')

function changeMessageText(newMsg) {
  message.value = newMsg
}

</script>

<style></style>
