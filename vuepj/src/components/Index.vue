<template>
    <div>
        <Input @add="handleAdd" />
        <List :list="state.list" @delete="handleDelete" />
        <button @click="clearList">清空</button>
    </div>
</template>

<script setup>
import Input from './Input.vue';
import List from './List.vue'
import { reactive } from 'vue';

const state = reactive({
    list: [
        {
            id: 'id-1',
            title: '标题1'
        },
        {
            id: 'id-2',
            title: '标题2'
        },
    ]
});
const handleAdd = (title) => {
    state.list.push({
        id: `id-${Date.now()}`,
        title
    })
} 

const handleDelete = (id) => {
    state.list = state.list.filter(item => item.id !== id)
}

const clearList = () => {
    state.list = []
}

</script>