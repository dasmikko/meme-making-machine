<template>
  <div class="top-bar-item" @click="$emit('click')">
    <slot></slot>  
  </div>
</template>

<script>
export default {
  
}
</script>

<style lang="scss">
  .top-bar-item {
    transition: all 100ms ease;
    @apply p-4 cursor-pointer;

    &:hover {
      @apply bg-grey-light;
    }
  }
</style>
