<template>
  <div id="app">
    <NavBanner/>
    <br>
    <br>
    <Uploader/>
    <router-view />

  </div>
</template>

<script>
import NavBanner from './components/NavBanner.vue'
import Uploader from './components/CsvUploader.vue'

export default {
  name: 'App',
  components: {
    NavBanner,
    Uploader,
  }
}
</script>

<style>
#app {
  font-family: 'Dongle', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
