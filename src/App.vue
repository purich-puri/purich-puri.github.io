<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </div>
  <router-view />
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Ubuntu&display=swap");

#app {
  font-family: "Ubuntu", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rgb(245, 245, 245);
}

#nav {
  position: fixed;
  left: 0;
  right: 0;
  padding: 30px;
}

#nav a {
  color: #fff;
}

#nav a.router-link-exact-active {
  font-weight: bold;
  color: #42b983;
}

/* Color Theme Swatches in Hex */
.bg-y-1 {
  background-color: #d9a404;
}
.bg-y-2 {
  background-color: #f2c438;
}
.bg-y-3 {
  background-color: #bf7e04;
}
.bg-y-4 {
  background-color: #8c5c03;
}
.bg-y-5 {
  background-color: #593202;
}
.bg-b-1 {
  background-color: #003273;
}
.bg-b-2 {
  background-color: #0456bf;
}
</style>
