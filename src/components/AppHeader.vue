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
  margin-top: 0px;
  background-color: green;
  color: white;
  text-align: center;
  font-size: 40px;
  padding: 10px;
  width: 100%;
}
</style>
