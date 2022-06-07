<script setup name="JinZhen">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import { ref } from 'vue'
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
    title: '最低价与开盘价差比',
    dataIndex: 'open_subtract_price_percent',
    key: 'open_subtract_price_percent',
  },
  {
    title: '最低价与收盘价差比',
    dataIndex: 'close_subtract_price_percent',
    key: 'close_subtract_price_percent',
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
  }
]
const dataSource = ref([])
</script>

<template>
  <div class="jin-zhen-component">
    <a-table :dataSource="dataSource" :columns="columns" />
  </div>
</template>
