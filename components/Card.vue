<template>
    <div class="card" :class="width">
      <span v-if="title" class="text-dark text-center text-xl block mb-5 font-bold">{{title}}</span>
      <slot></slot>
    </div>
</template>

<script>
  export default {
    name: 'Card',
    props: ['title', 'width']
  }
</script>

<style scoped>
.card {
  @apply rounded-lg overflow-hidden bg-white p-4 shadow-lg;
}
</style>
