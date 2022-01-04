<template>
  <div class="main flex flex-col justify-center items-center bg-y-3">
    <router-link to="/projects-collection">
      <div class="flex items-center wrap-button">
        <div class="text-4xl">PROJECTS</div>
        <img
          class="white-img animate-pulse"
          src="../assets/finger.png"
          alt=""
        />
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: "Projects",
  components: {},
};
</script>

<style scoped>
.main {
  height: 100%;
}

.wrap-button {
  border: 3px solid #f2c438;
  padding: 5px;
  border-radius: 16px;
}

@keyframes clickMeAni {
}
</style>
