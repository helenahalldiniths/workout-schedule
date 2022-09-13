<template>
  <nav>
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style scoped>
nav {
  background-color: rgb(254, 182, 34);
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 20px;
  width: 100%;
  font-size: 20px;
  padding-top: 5px;
}

nav a {
  color: black;
  font-weight: bold;
  text-decoration: none;
  padding: 5px 12px 8px 12px;
}

nav a.router-link-exact-active {
  color: black;
  background-color: white;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
}
</style>
