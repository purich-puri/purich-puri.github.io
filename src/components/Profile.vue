<template>
  <div class="main flex flex-col justify-center items-center bg-y-1">
    <div class="smoke-bg text-5xl font-extrabold">PURICH PURI</div>
    <div class="flippy p-2">
      <div>feed me plz!</div>
      <div class="flex flex-col justify-center">
        <div>MY WEAPONS</div>
        <div class="bg-circle flex justify-center">
          <img draggable="false" src="../assets/vue-js.png" alt="Vue logo" />
          <img
            draggable="false"
            class="object-scale-down"
            src="../assets/react-js.png"
            alt="React logo"
          />
          <img draggable="false" src="../assets/html-5.png" alt="html5 logp" />
          <img draggable="false" src="../assets/css3.png" alt="css3 logo" />
          <img
            draggable="false"
            src="../assets/javascript.png"
            alt="Javascript logo"
          />
        </div>
      </div>
      <div>I AM A WEB DEVELOPER!</div>
    </div>
  </div>
</template>

<style scoped>
.main {
  height: 100%;
  user-select: none;
  -webkit-user-select: none;
  -webkit-user-drag: none;
  -drag: none;
}

/* .smoke-bg {
  background-image: url(https://media.giphy.com/media/l3vRbTrGdpZrjjco8/giphy.gif);
  background-size: cover;
  color: transparent;
  -moz-background-clip: text;
  -webkit-background-clip: text;
} */

/* CREDIT TO THIS WEBSITE FOR GREAT CSS ANIMATION */
/* https://www.sliderrevolution.com/resources/css-text-animation/ */
.flippy {
  height: 80px;
  overflow: hidden;
}

.flippy > div {
  height: 50px;
  margin-bottom: 50px;
}

.flippy > div:first-child {
  animation: rotate-words 10s linear infinite;
}

@keyframes rotate-words {
  0% {
    margin-top: -270px;
  }
  5% {
    /* first div appear*/
    margin-top: -200px;
  }
  33% {
    margin-top: -200px;
  }
  38% {
    /* second div appear*/
    margin-top: -90px;
  }
  66% {
    margin-top: -90px;
  }
  71% {
    /* third div appear*/
    margin-top: 0px;
  }
  99.99% {
    margin-top: 0px;
  }
  100% {
    margin-top: -270px;
  }
}
</style>
