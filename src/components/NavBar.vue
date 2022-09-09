<template>
  <nav>
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
  </nav>
  <router-view />
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style scoped>
nav {
  padding: 5px;
  background-color: lightgray;
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 20px;
  width: 100%;
  font-size: 20px;
}

nav a {
  font-weight: bold;
  color: gray;
  text-decoration: none;
}

nav a.router-link-exact-active {
  color: black;
}
</style>
