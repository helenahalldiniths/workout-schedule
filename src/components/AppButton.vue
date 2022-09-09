<template>
  <button @click="$emit('button-clicked')" :style="{ background: color }">
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

<style scoped>
button {
  background: black;
  color: white;
  border: none;
  padding: 10px 15px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}

button:focus {
  outline: none;
}

button:active {
  transform: scale(0.98);
}
</style>
