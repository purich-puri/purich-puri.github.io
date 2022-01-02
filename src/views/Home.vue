<template>
  <div class="wrapper">
    <div class="sections">
      <div class="block">
        <Profile />
      </div>
      <div class="block">
        <Projects />
      </div>
      <div
        class="block flex flex-col justify-center items-center gap-10 bg-y-4"
      >
        <div>LINKS:</div>
        <div class="flex gap-5 bounce">
          <a href="https://github.com/purich-puri" target="_blank">
            <img
              class="logos toBounce"
              src="../assets/githubLogo/GitHub-Mark-64px.png"
              alt="github logo"
            />
          </a>
          <a href="https://github.com/purich-puri" target="_blank">
            <img
              class="logos toBounce"
              src="../assets/linkedinLogo/LI-In-Bug.png"
              alt="github logo"
            />
          </a>
        </div>
      </div>
      <div class="block flex justify-center bg-y-5 items-end p-2">
        <!-- <img class="object-scale-down" src="../assets/54.png" alt="" /> -->
        <div>PURICHPURI &copy; 2021</div>
      </div>
    </div>
  </div>
</template>

<script>
// import ProjectList from "../components/ProjectList.vue";
import Profile from "../components/Profile.vue";
import Projects from "../components/Projects.vue";

export default {
  name: "Home",
  components: {
    // ProjectList,
    Profile,
    Projects,
  },
};
</script>

<style scoped>
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

.logos {
  height: 32px;
  filter: brightness(0);
}

.bounce {
  width: auto;
}

.toBounce:hover {
  -webkit-animation: bounce 1s infinite;
}

@media screen and (max-width: 650px) {
  .block {
    width: 100%;
  }
}
@media screen and (max-height: 400px) {
  .block {
    width: 100%;
  }
}
</style>
