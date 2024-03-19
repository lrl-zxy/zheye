<template>
  <div class="dropdown" ref="dropdownRef">
    <a
      href="#"
      class="btn btn-outline-light my-2 dropdown-toggle"
      @click.prevent="toggleOpen"
    >
      {{ title }}
    </a>
    <ul class="dropdown-menu" :style="{ display: 'block' }" v-if="isOpen">
      <slot></slot>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { defineProps, ref, watch } from "vue";
import useClickOutside from "../../hooks/useClickOutside";
defineProps({
  title: {
    type: String,
  },
});
const isOpen = ref(false);
const toggleOpen = () => {
  isOpen.value = !isOpen.value;
};
const dropdownRef = ref<null | HTMLElement>(null);
const isClickOutside = useClickOutside(dropdownRef);
watch(isClickOutside, (newVal) => {
  if (newVal && isOpen.value) {
    isOpen.value = false;
  } else {
    isOpen.value = true;
  }
});
</script>

<style></style>
