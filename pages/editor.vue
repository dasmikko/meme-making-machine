<template>
    <section class="container">
      <Card>
        Edit the image <here class="."></here>
      </Card>
    </section>
</template>

<script>
  import Card from '../components/Card'
  export default {
    name: 'editor',
    components: {
      Card
    }
  }
</script>

<style scoped>
  .container {
    @apply min-h-screen flex justify-center items-center text-center mx-auto;
  }
</style>
