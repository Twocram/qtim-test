<script setup lang="ts">
interface Props {
  variant?: 'default' | 'rounded'
}

withDefaults(defineProps<Props>(), {
  variant: 'default'
})
</script>

<template>
  <button class="v-button" :class="[variant]">
    <slot />
  </button>
</template>

<style scoped>
.v-button {
  width: 100%;
  border-radius: 999px;
  padding: 16px 32px;
  font-size: 20px;
  line-height: 100%;
  white-space: nowrap;
  cursor: pointer;
}

.v-button.default {
  background: var(--black-color);
  color: var(--white-color);
  border: 1px solid var(--black-color);
}

.v-button.rounded {
  width: 52px;
  height: 52px;
  padding: 14px;
  border-radius: 999px;
  background: unset;
  border: 2px solid #0000001A;
}

</style>
