<template>
  <section class="canvas-wrap">
    <div class="canvas" ref="canvasRoot">
      <!-- This is where FabricJS/Selecto-managed DOM or <canvas> will live -->
      <p class="placeholder">
        Canvas Area
        <small>Implement FabricJS/Selecto here.</small>
      </p>
    </div>
  </section>
</template>

<script setup>
import { onMounted, ref } from 'vue'

const canvasRoot = ref(null)

onMounted(() => {
  // Placeholder: initialize FabricJS or Selecto here in the future.
  // Example (pseudo):
  // const fabricCanvas = new fabric.Canvas(canvasRoot.value)
})
</script>

<style scoped>
.canvas-wrap {
  display: grid;
  place-items: center;
  width: 100%;
  height: 100%;
  background: #f3f4f6;
}
.canvas {
  width: min(920px, calc(100% - 32px));
  height: min(600px, calc(100% - 32px));
  background: white;
  box-shadow: 0 10px 25px rgba(0,0,0,0.08);
  border: 1px solid #e5e7eb;
  border-radius: 10px;
  position: relative;
  overflow: hidden;
}
.placeholder {
  position: absolute;
  inset: 0;
  display: grid;
  place-items: center;
  color: #9ca3af;
  font-weight: 600;
}
.placeholder small { display: block; font-weight: 400; }
</style>
