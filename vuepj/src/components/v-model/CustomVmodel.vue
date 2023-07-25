<template>
    <!-- 例如：vue 颜色选择器 -->
    <input type="text" 
    :value="modelValue" 
    @input="$emit('update:modelValue', $event.target.value)">
</template>

<script setup>
const props = defineProps(['modelValue'])

const emit = defineEmits(['update:modelValue'])
</script>