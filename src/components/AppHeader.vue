<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <header>
    <h1>{{ title }}</h1>
  </header>
  <NavBar />
</template>

<script>
import NavBar from "./NavBar.vue";
export default {
  name: "AppHeader",
  props: {
    title: String,
  },
  components: {
    NavBar,
  },
};
</script>

<style scoped>
h1 {
  margin-bottom: 0px;
  margin-top: 0px;
  background-color: rgb(59, 90, 110);
  color: white;
  text-align: center;
  font-size: 40px;
  padding: 10px;
  width: 100%;
}
</style>
