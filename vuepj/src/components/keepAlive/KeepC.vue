<template>
    <p>state C</p>
</template>

<script setup>
import { onMounted, onUnmounted } from 'vue';
    onMounted(()=>{
        console.log("C mounted");
    })
    onUnmounted(() =>{
        console.log("C unMounted");
    })
</script>