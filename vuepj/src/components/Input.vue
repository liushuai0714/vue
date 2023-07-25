<template>
    <input type="text" v-model="title" id="input1" @keyup.enter.native = addTitle>
    <button class="plus" @click=addTitle>add</button>
</template>

<script setup>
import {ref} from 'vue'

const title = ref('')
const emit = defineEmits(['add'])
const addTitle = () => {
    emit('add', title.value);
    title.value = '';
}

defineExpose({
    title,
    addTitle
})
</script>

<style scoped>
.plus{
    margin-left: 5px;
}
</style>