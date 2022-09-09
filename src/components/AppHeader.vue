<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <header>
    <h1>{{ title }}</h1>
  </header>
</template>

<script>
export default {
  name: "AppHeader",
  props: {
    title: String,
  },
};
</script>

<style scoped>
h1 {
  margin-bottom: 0px;
  background-color: grey;
  color: white;
}
</style>
