<template>
  <aside class="left-menu">
    <section>
      <h3>Text</h3>
      <button class="item" @click="$emit('addText')">Add Text</button>
    </section>
    <section>
      <h3>Shapes</h3>
      <div class="grid">
        <button class="shape" title="Square" @click="$emit('addShape','rect')">■</button>
        <button class="shape" title="Circle" @click="$emit('addShape','circle')">●</button>
        <button class="shape" title="Rectangle" @click="$emit('addShape','rectangle')">▭</button>
      </div>
    </section>
    <section>
      <h3>Images</h3>
      <input type="file" accept="image/*" @change="onUpload" />
    </section>
  </aside>
</template>

<script setup>
const emit = defineEmits(['addText','addShape','addImage'])

function onUpload(e) {
  const file = e.target.files?.[0]
  if (file) emit('addImage', file)
  e.target.value = ''
}
</script>

<style scoped>
.left-menu {
  width: 240px;
  border-right: 1px solid #e5e7eb;
  padding: 12px;
  background: #fafafa;
  overflow: auto;
}
section { margin-bottom: 16px; }
h3 { font-size: 14px; margin: 0 0 8px; color: #374151; }
.item {
  display: block;
  width: 100%;
  padding: 8px 10px;
  border: 1px solid #d1d5db;
  border-radius: 6px;
  background: white;
  cursor: pointer;
}
.grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 6px; }
.shape {
  height: 36px;
  border: 1px solid #d1d5db;
  border-radius: 6px;
  background: white;
  cursor: pointer;
}
</style>
