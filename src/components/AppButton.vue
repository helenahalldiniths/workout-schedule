<template>
  <button
    class="btn"
    @click="$emit('button-clicked')"
    :style="{ background: color }"
  >
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "AppButton",
  props: {
    color: String,
    text: String,
  },
};
</script>
