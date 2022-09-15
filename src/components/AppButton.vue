<template>
  <button
    class="btn"
    @click="$emit('button-clicked')"
    :style="{ background: props.color }"
  >
    {{ props.text }}
  </button>
</template>

<script setup>
const props = defineProps({
  text: String,
  color: String,
});
</script>
