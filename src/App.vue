<template>
  <AppHeader title="Workout plan" />
  <NavBar />
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import NavBar from "./components/NavBar.vue";

export default {
  name: "App",
  components: {
    AppHeader,
    NavBar,
  },
};
</script>

<style>
#app {
  font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
