<template>
  <div class="container">
    <GlobalHeader :user="user"/>
    <ColumnList :list="testData" />
  </div>
</template>

<script setup lang="ts">
import { reactive } from "vue";
import "bootstrap/dist/css/bootstrap.min.css";
import ColumnList, { ColumnProps } from "./components/ColumnList/index.vue";
import GlobalHeader,{UserProps} from "@/components/GlobalHeader/index.vue";
const user:UserProps={
  isLogin:true,
  name:'张三',
  id:1,
  nickName:'张三'
}
const testData: ColumnProps[] = reactive([
  {
    id: 1,
    title: "test01",
    avatar:
      "https://www.baidu.com/img/PCtm_d9c8750bed0b3c7d089fa7d55720d6cf.png",
    description: "我就是测试",
  },
  {
    id: 2,
    title: "test01",
    // avatar:
    //   "https://www.baidu.com/img/PCtm_d9c8750bed0b3c7d089fa7d55720d6cf.png",
    description: "我就是测试",
  },
  {
    id: 3,
    title: "test01",
    avatar:
      "https://www.baidu.com/img/PCtm_d9c8750bed0b3c7d089fa7d55720d6cf.png",
    description: "我就是测试",
  },
  {
    id: 3,
    title: "test01",
    avatar:
      "https://www.baidu.com/img/PCtm_d9c8750bed0b3c7d089fa7d55720d6cf.png",
    description: "我就是测试",
  },
]);
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
