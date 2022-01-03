<template>
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

.wrapper {
  height: 100vh;
  border: 20px solid #fff;
}

.sections {
  height: 100%;
  display: flex;
  flex-wrap: wrap;
}

.block {
  width: 50%;
  height: calc(100% / 2);
}

@media screen and (max-width: 650px) {
  .block {
    width: 100%;
  }
}
@media screen and (max-height: 500px) {
  .block {
    width: 100%;
  }
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
