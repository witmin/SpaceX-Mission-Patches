<template>
  <div id="app">
    <MissionPatches msg="SpaceX Mission Patches"/>
  </div>
</template>

<script>
import MissionPatches from './components/MissionPatches.vue'

export default {
  name: 'app',
  components: {
    MissionPatches
  }
}
</script>

<style src="./styles/app.scss" lang="scss">
</style>
