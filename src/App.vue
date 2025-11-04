<script setup>
import TopBar from './components/TopBar.vue'
import LeftMenu from './components/LeftMenu.vue'
import CanvasArea from './components/CanvasArea.vue'

function noop() {}
</script>

<template>
  <div class="layout">
    <TopBar @newDesign="noop" @saveDesign="noop" @exportDesign="noop" />
    <div class="body">
      <LeftMenu @addText="noop" @addShape="noop" @addImage="noop" />
      <CanvasArea />
    </div>
  </div>
</template>

<style scoped>
.layout {
  display: flex;
  flex-direction: column; /* topbar + body */
  min-height: 100vh;
  width: 100%;
}
.body {
  display: flex; /* left menu + canvas area */
  flex: 1 1 auto;
  min-height: 0; /* allow children to size for overflow */
}
</style>
