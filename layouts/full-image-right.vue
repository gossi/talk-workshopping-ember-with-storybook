<script setup lang="ts">
import { handleBackground } from '@slidev/theme-apple-basic/layoutHelper';
import { computed } from 'vue';

const props = defineProps({
  image: {
    type: String
  },
  class: {
    type: String
  }
});
const style = computed(() => handleBackground(props.image));
</script>

<template>
  <div class="grid grid-cols-2 w-full h-full">
    <div class="slidev-layout default image-right" :class="props.class">
      <slot />
    </div>
    <div :style="style" />
  </div>
</template>
