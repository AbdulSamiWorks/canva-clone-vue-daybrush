<template>
  <div class="row">
    <select
      class="ctrl"
      v-model="local.fontFamily"
      @change="$emit('commit', 'fontFamily', local.fontFamily)"
    >
      <option>Arial, sans-serif</option>
      <option>Georgia, serif</option>
      <option>Courier New, monospace</option>
    </select>
    <select
      class="ctrl"
      v-model="local.direction"
      @change="$emit('commit', 'direction', local.direction)"
    >
      <option value="ltr">LTR</option>
      <option value="rtl">RTL</option>
    </select>
    <input
      class="ctrl"
      type="number"
      min="8"
      max="200"
      v-model.number="local.fontSize"
      @change="$emit('commit', 'fontSize', local.fontSize)"
    />
    <input
      class="ctrl"
      type="color"
      v-model="local.color"
      @input="$emit('commit', 'color', local.color)"
    />
    <button
      class="btn"
      :class="{ toggled: local.bold }"
      @click="$emit('toggle', 'bold')"
    >
      B
    </button>
    <button
      class="btn"
      :class="{ toggled: local.italic }"
      @click="$emit('toggle', 'italic')"
    >
      <i>I</i>
    </button>
    <button
      class="btn"
      :class="{ toggled: local.underline }"
      @click="$emit('toggle', 'underline')"
    >
      <u>U</u>
    </button>
    <select
      class="ctrl"
      v-model="local.textAlign"
      @change="$emit('commit', 'textAlign', local.textAlign)"
    >
      <option value="left">Left</option>
      <option value="center">Center</option>
      <option value="right">Right</option>
    </select>
    <label class="label"
      >Line
      <input
        class="ctrl small"
        type="number"
        step="0.1"
        min="0.8"
        max="3"
        v-model.number="local.lineHeight"
        @change="$emit('commit', 'lineHeight', local.lineHeight)"
    /></label>
    <label class="label"
      >Space
      <input
        class="ctrl small"
        type="number"
        step="0.5"
        min="-2"
        max="10"
        v-model.number="local.letterSpacing"
        @change="$emit('commit', 'letterSpacing', local.letterSpacing)"
    /></label>
    <label class="label"
      >BG
      <input
        class="ctrl"
        type="color"
        v-model="local.bgColor"
        @input="$emit('commit', 'bgColor', local.bgColor)"
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
        @change="$emit('commit', 'opacity', local.opacity)"
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
defineEmits(["commit", "toggle"]);
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
.btn {
  height: 32px;
  padding: 0 12px;
  border-radius: 6px;
  border: 1px solid #d1d5db;
  background: #fff;
  cursor: pointer;
}
.btn.toggled {
  background: #e5e7eb;
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
