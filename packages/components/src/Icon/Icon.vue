<template>
  <div class="albe-icon">
    <svg class="icon" aria-hidden="true">
      <use :xlink:href="iconName"></use>
    </svg>
    <div v-if="dot" class="albe-info" :class="styleDot">{{ badge }}</div>
  </div>
</template>
<script lang="ts" setup>
import "./font/iconfont.js";
import "./style/index.less";
import { computed } from "vue";
import { iconProps } from "./types";

const props = defineProps(iconProps);

const iconName = computed(() => {
  return `#albe-${props.name}`;
});
const styleDot = computed(() => {
  return {
    [`albe-dot`]: props.dot && !props.badge,
  };
});
const badge = computed(() => {
  return props.badge;
});
</script>
