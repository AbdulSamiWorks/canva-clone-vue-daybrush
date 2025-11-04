<template>
  <div class="row">
    <label class="label"
      >Fill
      <input
        class="ctrl"
        type="color"
        v-model="local.fill"
        @input="$emit('commit', 'fill', local.fill)"
    /></label>
    <label class="label"
      >Stroke
      <input
        class="ctrl"
        type="color"
        v-model="local.stroke"
        @input="$emit('commit', 'stroke', local.stroke)"
    /></label>
    <label class="label"
      >Width
      <input
        class="ctrl small"
        type="number"
        min="0"
        max="20"
        v-model.number="local.strokeWidth"
        @change="$emit('commit', 'strokeWidth', local.strokeWidth)"
    /></label>
    <label class="label" v-if="local.shape !== 'circle'"
      >Radius
      <input
        class="ctrl small"
        type="number"
        min="0"
        max="100"
        v-model.number="local.cornerRadius"
        @change="$emit('commit', 'cornerRadius', local.cornerRadius)"
    /></label>
    <label class="label"
      >Opacity
      <input
        class="ctrl"
        type="range"
        min="0"
        max="1"
        step="0.05"
        v-model.number="local.opacity"
        @input="$emit('commit', 'opacity', local.opacity)"
    /></label>
    <label class="label"
      >Rotate
      <input
        class="ctrl small"
        type="number"
        step="1"
        min="-180"
        max="180"
        v-model.number="local.rotation"
        @change="$emit('commit', 'rotation', local.rotation)"
    /></label>
  </div>
</template>

<script setup>
import { reactive, watch } from "vue";
const props = defineProps({ selected: { type: Object, required: true } });
defineEmits(["commit"]);
const local = reactive({});
watch(
  () => props.selected,
  (val) => {
    Object.keys(local).forEach((k) => delete local[k]);
    if (val) Object.assign(local, val);
  },
  { immediate: true }
);
</script>

<style scoped>
.row {
  display: flex;
  align-items: center;
  gap: 8px;
}
.ctrl {
  height: 28px;
}
.ctrl.small {
  width: 60px;
}
.label {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  font-size: 12px;
  color: #374151;
}
</style>
