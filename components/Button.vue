<template>
  <button class="button" :class="classes">
    <slot></slot>  
  </button>  
</template>

<script>
export default {
  name: 'Button',
  props: [
    'isPrimary',
    'isSuccess',
    'isWarning',
    'isDanger'
  ],
  computed: {
    classes: function () {
      let classList = []
      if (this.isPrimary) classList.push('is-primary')
      return classList.join(' ')
    }
  }
}
</script>

<style lang="scss">
.button {
  @apply p-3 bg-green-light rounded-lg text-white;

  &:hover {
    @apply bg-green;
  } 

  &.is-primary {
    @apply bg-purple-light;

    &:hover {
      @apply bg-purple;
    }
  }
}
</style>
