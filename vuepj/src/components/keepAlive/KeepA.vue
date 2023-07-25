<template>
    <p>state A</p>
</template>

<script setup>
import { onMounted, onUnmounted } from 'vue';
    onMounted(()=>{
        console.log("A mounted");
    })
    onUnmounted(() =>{
        console.log("A unMounted");
    })
</script>