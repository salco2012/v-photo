<template>
  <div id="app">
    <PhotoProcessing/>
  </div>
</template>

<script>
import PhotoProcessing from './components/PhotoProcessing.vue'

export default {
  name: 'App',
  components: {
    PhotoProcessing
  }
}
</script>

<style lang="scss">
body{
  font-family: Arial, Helvetica, sans-serif;
}
</style>
