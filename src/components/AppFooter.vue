<template>
  <footer>
    <nav class="footer-links">
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
    </nav>
    <div class="copyright">Workout plan © 2022</div>
  </footer>
</template>

<style scoped>
footer {
  width: 100%;
  background-color: rgb(59, 90, 110);
  text-align: center;
  min-height: 50px;
  color: lightgray;
}

nav {
  display: flex;
  justify-content: center;
  gap: 20px;
  padding: 5px;
  color: lightgray;
}
nav a {
  color: lightgray;
  text-decoration: none;
}

nav a.router-link-exact-active {
  color: lightgray;
}

.copyright {
  font-size: 12px;
}
</style>
