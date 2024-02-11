<template>
    <div>
       Hello Counter: {{ messageTextFromProp }}
    </div>
    <div>
        <input type="text" v-model="message">
        <button @click="changeMessageText(message)">Change Message from counter</button>
    </div>
        <div>
            <button @click="increaseCounter">Click increase {{ count }}</button>
        </div>
</template>
    
<script setup lang='ts'>
import { ref } from 'vue';

defineProps({
    messageTextFromProp: String,
    changeMessageText: Function
})
    const count = ref(0)
    const message = ('')
    function increaseCounter() {
        count.value +=1
    }
</script>
    
<style>
    
</style>