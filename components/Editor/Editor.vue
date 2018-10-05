<template>
    <div class="main-editor-view">
      main editor view

      <VueDragResize :isActive="true" :w="200" :h="200" :parentLimitation="true" v-on:resizing="resize" v-on:dragging="resize">
        <h3>Hello World!</h3>
        <p>{{ top }} х {{ left }} </p>
        <p>{{ width }} х {{ height }}</p>
      </VueDragResize>
    </div>
</template>

<script>
  import VueDragResize from 'vue-drag-resize'
  export default {
    name: 'Editor',
    components: {
      VueDragResize
    },
    data() {
      return {
        width: 0,
        height: 0,
        top: 0,
        left: 0
      }
    },

    methods: {
      resize(newRect) {
        this.width = newRect.width;
        this.height = newRect.height;
        this.top = newRect.top;
        this.left = newRect.left;
      }
    }
  }
</script>

<style scoped>
.main-editor-view {
  @apply relative min-h-full;
}
</style>
