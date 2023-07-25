<template>
    <p>{{ name }}</p>
    <CustomVmodel v-model="name"/>
</template>

<script setup>
import CustomVmodel from './CustomVmodel.vue'
import { ref } from 'vue'

const name = ref('双越')
</script>