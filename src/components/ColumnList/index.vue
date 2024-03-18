<template>
  <div class="row">
    <div class="col-4 card" v-for="item in list" :key="item.id">
      <img class="card-img-top" :src="item.avatar" :alt="item.title" />
      <h5 class="card-title">{{ item.title }}</h5>
      <p class="card-text">{{ item.description }}</p>
      <a class="btn btn-outline-primary" href="#">进入专栏</a>
    </div>
  </div>
</template>
<script setup lang="ts">
import { PropType, defineProps,computed } from "vue";
export interface ColumnProps {
  id: number;
  title: string;
  avatar?: string;
  description: string;
}
const props = defineProps({
  list: {
    type: Array as PropType<ColumnProps[]>,
    required: true,
  },
});
const list = computed(()=>{
    return props.list.map((item)=>{
        if(!item.avatar) item.avatar = require('@/assets/logo.png')
        return item
    })
})
</script>
<style></style>
