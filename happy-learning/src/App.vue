<template>
  <div id="app">
    <JsFundation></JsFundation>
  </div>
</template>

<script>
import JsFundation from '@/components/jsFundation.vue'
export default {
  name: 'App',
  components: {
    JsFundation
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
