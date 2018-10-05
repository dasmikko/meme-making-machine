<template>
  <div class="top-bar">
    <div class="logo">
      MemeMakingMachine
    </div>
    <TopBarItem v-on:click="onClick">Files</TopBarItem>
    <TopBarItem v-on:click="onClick">About</TopBarItem>
  </div>
</template>

<script>
import TopBarItem from './TopBarItem.vue'
export default {
  name: 'TopBar',
  components: {
    TopBarItem
  },
  methods: {
    onClick () {
      console.log('Clicked dude')
    }
  }
}
</script>

<style lang="scss">
.top-bar {
  @apply flex border-b;  
}

.logo {
  @apply p-4 font-bold
}
</style>
