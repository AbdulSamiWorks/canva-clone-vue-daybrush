<template>
  <header class="topbar">
    <h1 class="brand">Canva Clone</h1>
    <div class="actions">
      <button class="btn" @click="$emit('newDesign')">New</button>
      <button class="btn" @click="$emit('saveDesign')">Save</button>
      <button class="btn primary" @click="$emit('exportDesign')">Export</button>
    </div>
  </header>
</template>

<script setup>
// No props yet; emitting simple events for future wiring
</script>

<style scoped>
.topbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 56px;
  padding: 0 16px;
  border-bottom: 1px solid #e5e7eb;
  background: #ffffff;
}
.brand {
  font-size: 18px;
  margin: 0;
}
.actions { display: flex; gap: 8px; }
.btn {
  height: 32px;
  padding: 0 12px;
  border-radius: 6px;
  border: 1px solid #d1d5db;
  background: #fff;
  cursor: pointer;
}
.btn.primary {
  background: #42b883;
  border-color: #42b883;
  color: white;
}
.btn:active { transform: translateY(1px); }
</style>
