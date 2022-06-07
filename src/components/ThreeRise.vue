<script setup name="ThreeRise">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import { ref } from 'vue'
import axios from 'axios'
const columns = [
  {
    title: '日期',
    dataIndex: 'date',
    key: 'date',
  },
  {
    title: '代码',
    dataIndex: 'code',
    key: 'code',
  },
  {
    title: '代码名称',
    dataIndex: 'code_name',
    key: 'code_name',
  },
  {
    title: '开盘价',
    dataIndex: 'open',
    key: 'open',
  },
  {
    title: '最低价',
    dataIndex: 'low',
    key: 'low',
  },
  {
    title: '收盘价',
    dataIndex: 'close',
    key: 'close',
  },
  {
    title: '最高价',
    dataIndex: 'high',
    key: 'high',
  },
  {
    title: '成交量',
    dataIndex: 'volume',
    key: 'volume',
  },
  {
    title: '成交额',
    dataIndex: 'amount',
    key: 'amount',
  },
  {
    title: '换手率',
    dataIndex: 'turn',
    key: 'turn',
  },
  {
    title: '涨跌幅',
    dataIndex: 'pctChg',
    key: 'pctChg',
  },
  {
    title: '三日涨跌幅',
    dataIndex: 'three_days_chg',
    key: 'three_days_chg',
  }
]
const dataSource = ref([])
// 为给定 ID 的 user 创建请求
axios.get('http://r.luck101.xyz:8888/v1d0/three-day-raise')
  .then(function (response) {
    dataSource.value = response?.data || []
  })
  .catch(function (error) {
    console.log(error);
  });
</script>

<template>
  <div class="three-rise-component">
    <a-table :dataSource="dataSource" :columns="columns" />
  </div>
</template>
