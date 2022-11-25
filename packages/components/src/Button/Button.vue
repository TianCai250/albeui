<template>
  <button class="al-button" :class="styleClass">
    <slot />
  </button>
</template>

<script lang="ts" setup>
import "./style/index.less";
import { computed } from "vue";
import { buttonProps } from "./types";

const props = defineProps(buttonProps);

const styleClass = computed(() => {
  return {
    [`al-button--${props.type}`]: props.type,
    "is-plain": props.plain,
    "is-round": props.round,
    "is-disabled": props.disabled,
    [`al-button--${props.size}`]: props.size,
  };
});
</script>
