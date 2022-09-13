<template>
  <body>
    <AppHeader title="Workout plan" />
    <router-view />
    <AppFooter class="footer" />
  </body>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import AppFooter from "./components/AppFooter.vue";

export default {
  name: "App",
  components: {
    AppHeader,
    AppFooter,
  },
};
</script>

<style>
body {
  margin: 0px;
  height: 100vh;
  display: flex;
  flex-direction: column;
}

.footer {
  margin-top: auto;
}

#app {
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
  color: rgb(59, 90, 110);
}

.btn,
.big-btn {
  color: white;
  background: rgb(59, 90, 110);

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
  color: white;
  background: rgb(59, 90, 110);
}

.btn:focus {
  outline: none;
}

.btn:active {
  transform: scale(0.98);
}
</style>
