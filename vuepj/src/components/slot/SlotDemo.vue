<template>
    <p>{{ name }}</p>
    <a :href="url">
        <slot>
            默认内容
        </slot>
    </a>
</template>

<script setup>
const props = defineProps(['url', 'name'])
</script>