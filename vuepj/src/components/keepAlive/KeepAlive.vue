<template>
    <button @click="changeState('A')">A</button>
    <button @click="changeState('B')">B</button>
    <button @click="changeState('C')">C</button>
    <keep-alive>
        <KeepA v-if="state === 'A'" />
    </keep-alive>
    <keep-alive>
        <KeepB v-if="state === 'B'" />
    </keep-alive>
    <keep-alive>
        <KeepC v-if="state === 'C'" />
    </keep-alive>
</template>

<script setup>
import KeepA from './KeepA.vue';
import KeepB from './KeepB.vue';
import KeepC from './KeepC.vue';
import { ref } from 'vue';

const state = ref('A')
const changeState = (s) => {
    state.value = s
} 
</script>