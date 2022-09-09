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
  color: black;
}

.btn,
.big-btn {
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

.big-btn {
  font-size: 20px;
  background: green;
}

.btn:focus {
  outline: none;
}

.btn:active {
  transform: scale(0.98);
}

body {
  margin: 0px;
}
</style>
