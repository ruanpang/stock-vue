<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup

import { ref, shallowRef } from 'vue'
import JinZhen from './components/JinZhen.vue'
import ThreeRise from './components/ThreeRise.vue';

import zhCN from 'ant-design-vue/es/locale/zh_CN';
import dayjs from 'dayjs';
import 'dayjs/locale/zh-cn';
dayjs.locale('zh-cn');
const locale = ref(zhCN)
const moduleList = shallowRef([])
moduleList.value = [
  { name: '金针探底', component: JinZhen },
  { name: '三日连续上涨', component: ThreeRise }
]


const getCurrentTime = () => {
  return dayjs().format('YYYY-MM-DD HH:mm:ss')
}
const setCurrentTime = () => {
  currentTime.value = getCurrentTime()
}
const currentTime = ref(getCurrentTime())

setInterval(() => {
  setCurrentTime()
}, 1000)
</script>

<template>
  <a-config-provider :locale="locale">
    <h1><span>当前时间为:</span><span>{{currentTime}}</span></h1>
    <div class="gutter-example">
      <a-row type="flex" :gutter="[16, 16]">
        <a-col flex="100%" v-for="(item, key) in moduleList" :key="key">
          <div class="gutter-box">
            <a-card :title="item.name" bordered>
              <component :is="item.component"></component>
            </a-card>
          </div>
        </a-col>
      </a-row>
    </div>
  </a-config-provider>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background: #d3d3d3;
  height: 100%;
  width: 100%;
}
</style>
