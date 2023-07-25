<template>
    <ul>
        <li v-for="item in props.list" :key="item.id">{{ item.title }}
        <button @click="deleteLi(item.id)">delete</button>
        </li>
    </ul>
</template>

<script setup>
const props = defineProps({
    list: {
        type: Array,
        default() {
            return []
        }
    }
})
const emit = defineEmits(['delete'])
const deleteLi = (id) => {
    emit('delete', id)
}
defineExpose({
    deleteLi,
})
</script>