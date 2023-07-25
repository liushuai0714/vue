<template>
    <SlotDemo :url="data.website.url" :name="name">
        {{ data.website.title }}
    </SlotDemo>

    <ScopedSlotDemo :url="data.website.url">
        <!-- 作用域插槽 -->
        <template v-slot="slotProps">
            {{ slotProps.slotData.title }}
        </template>

        <!-- 具名插槽 -->
        <template v-slot:footer>
            <!-- 缩写 -->
        <!-- <template #footer> -->
            {{ data.website.subTitle }}
        </template>
    </ScopedSlotDemo>
</template>

<script setup>
import { reactive, ref } from 'vue';
import SlotDemo from './SlotDemo.vue'
import ScopedSlotDemo from './ScopedSlotDemo.vue'

const name = ref('小麻痹')
const data = reactive({
    website:{
        url: 'http://www.baidu.com',
        title: 'baidu',
        subTitle: '百度'
    }
})
</script>