<template>
    <a :href="url">
        <!-- 作用域插槽 -->
        <slot :slotData="data.website">
            {{ data.website.subTitle }}
        </slot>
    </a>
    <!-- 具名插槽 -->
    <slot name="footer">

    </slot>
</template>

<script setup>
import { reactive } from 'vue';

const props = defineProps(['url'])
const data = reactive({
    website: {
        url: 'http://www.jd.com',
        title: 'jingdong',
        subTitle: '京东'
    }
})
</script>