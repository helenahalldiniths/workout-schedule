<template>
  <h1>Workout plan</h1>
  <nav>
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
  </nav>
  <router-view />
</template>

<style>
#app {
  font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

h1 {
  margin-bottom: 0px;
  background-color: grey;
  color: white;
}
nav {
  padding: 5px;
  background-color: lightgray;
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 20px;
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
