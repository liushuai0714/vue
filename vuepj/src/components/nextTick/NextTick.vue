<template>
    <ul ref="ul1"><li v-for="(item, index) in list" :key="index">{{ item }}</li></ul>
    <button @click="addItem">添加一项</button>
</template>

<!-- <script setup>

import { nextTick, reactive, ref } from 'vue';

const data = reactive({
    list: ['a','b', 'c']
})
//获取DOM元素 必须在DOM渲染完成后才可以获取
const ul = ref()

const addItem = () => {
    data.list.push(`${Date.now()}`)
    console.log(ul.value.childNodes.length);
}
</script> -->

<script>
export default {
    data() {
        return {
            list: ['a', 'b', 'c']
        }
    },
    methods: {
        addItem() {
            this.list.push(`${Date.now()}`)
            this.$nextTick(() => {
                //获取DOM元素
                const uli = this.$refs.ul1
                console.log(uli.childNodes.length);
            })
        }
    },
}

</script>