<template>
    <p>state B</p>

</template>

<script setup>
import { onMounted, onUnmounted } from 'vue';
    onMounted(()=>{
        console.log("B mounted");
    })
    onUnmounted(() =>{
        console.log("B unMounted");
    })
</script>