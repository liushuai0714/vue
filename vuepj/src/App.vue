<template>

  <ul class="ul">
    <li class='li' v-for="(item, index) in list" :key="index" @click="change(index)">{{ item.name }}</li>
  </ul>
  <!-- 动态组件 -->
  <keep-alive>
    <component :is="currentTab.com" />
  </keep-alive>
  <Line/>
</template>

<script setup>
// import Index from './components/Index.vue'
// import Index from './components/v-model/index.vue';
import NextTick from './components/nextTick/NextTick.vue';
import Index from './components/slot/Index.vue';
import KeepAlive  from './components/keepAlive/KeepAlive.vue';
import { defineAsyncComponent, markRaw, reactive, ref } from 'vue';
import  index from './components/v-model/index.vue';
import Line from './components/line.vue'

import * as echarts from "echarts";
import { provide } from "vue";
provide("echarts", echarts);

//加载 异步组件
const FormDemo = defineAsyncComponent(() => 
  import('./components/FormDemo.vue')
)

let list = reactive([
  {
    name: '组件1',
    com: markRaw(NextTick),
  },
  {
    name: '插槽',
    com: markRaw(Index),
  },
  {
    name: '异步组件',
    com: markRaw(FormDemo),
  },
  {
    name: 'keep-alove',
    com: markRaw(KeepAlive),
  },
  {
    name: '自定义v-model',
    com: markRaw(index),
  },
])

let currentTab = reactive({
  com: list[0].com
})

const change = (index) => {
  currentTab.com = list[index].com
} 
</script>


<style scoped>
.ul {
  overflow: hidden;
}

.ul .li {
  float: left;
  list-style: none;
  margin-right: 5px;
  cursor: pointer;
}
</style>
