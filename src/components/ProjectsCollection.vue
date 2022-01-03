<template>
  <div id="nav">
    <router-link to="/">GO BACK</router-link>
  </div>
  <div class="hamNav">
    <div>
      <div></div>
      <div></div>
      <div></div>
    </div>
  </div>

  <div class="wrapper">
    <div class="sections">
      <div
        class="projectTitle block flex justify-center items-center text-4xl bg-y-1"
      >
        {{ myProjects[this.state.picker].name.toUpperCase() }}
      </div>
      <div class="block flex flex-wrap justify-center items-center bg-y-3">
        {{ myProjects[this.state.picker].description }}
      </div>
      <div class="block flex justify-center items-center bg-y-4">
        <div class="flex w-full gap-1 justify-around">
          <div class="flex-1"></div>
          <div
            class="flex-1"
            v-if="myProjects[this.state.picker].liveLink !== ''"
          >
            <button
              @click="goToLink(myProjects[this.state.picker].liveLink)"
              class="buttons"
            >
              LIVE
            </button>
          </div>
          <div class="flex-1">
            <button
              @click="goToLink(myProjects[this.state.picker].repo)"
              class="buttons"
            >
              GIT REPO
            </button>
          </div>
          <div class="flex-1"></div>
        </div>
      </div>
      <div class="block flex flex-col justify-center items-center bg-y-5">
        <div v-for="(project, index) in myProjects" :key="index">
          <div class="cursor-pointer" @click="projectId(index)">
            {{ project.name }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { reactive } from "@vue/reactivity";
export default {
  name: "ProjectsCollection",
  components: {},
  methods: {
    projectId(id) {
      this.state.picker = id;
    },
    goToLink(link) {
      window.open(link);
    },
  },
  data() {
    const state = reactive({
      picker: 0,
    });

    return {
      state,
      myProjects: [
        {
          name: "Pokemon App",
          description: "",
          liveLink: "https://purich-puri.github.io/pokemon-app/",
          repo: "https://github.com/purich-puri/pokemon-app",
        },
        {
          name: "Tracker App",
          description: "",
          liveLink: "",
          repo: "https://github.com/purich-puri/tracker-app",
        },
        {
          name: "Get Random User",
          description: "",
          liveLink: "",
          repo: "https://github.com/purich-puri/get-random-user",
        },
        {
          name: "Library",
          description: "A small library site to learn the fundamental of CRUD",
          liveLink: "https://purich-puri.github.io/odin-library/",
          repo: "https://github.com/purich-puri/odin-library",
        },
        {
          name: "Calculator",
          description: "A Calculator app using pure JS.",
          liveLink: "https://purich-puri.github.io/odin-calculator/",
          repo: "https://github.com/purich-puri/odin-calculator/",
        },
        {
          name: "Rock Paper Scissor",
          description: "",
          liveLink: "https://purich-puri.github.io/odin-rps/",
          repo: "https://github.com/purich-puri/odin-rps/",
        },
        {
          name: "Pocket Planner",
          description: "",
          liveLink: "",
          repo: "https://github.com/purich-puri/PocketPlanner",
        },
        {
          name: "Get Invited",
          description: "",
          liveLink: "",
          repo: "https://github.com/purich-puri/getInvited",
        },
        {
          name: "Math It",
          description: "",
          liveLink: "",
          repo: "https://github.com/purich-puri/Math-It",
        },
        {
          name: "My Password Storage",
          description: "",
          liveLink: "",
          repo: "https://github.com/purich-puri/MyPasswordStorage",
        },
      ],
    };
  },
};
</script>

<style scoped>
#nav {
  position: fixed;
  font-size: 0.85rem;
  text-align: start;
  left: 0;
  right: 0;
  top: 0;
  padding: 0 20px;
  color: #000;
  background-color: #fff;
}

.hamNav {
  position: fixed;
  left: 50%;
  top: 50%;
  margin-left: -25px;
  margin-top: -25px;
  width: 50px;
  height: 50px;
  background-color: #fff;
  border-radius: 15%;
  cursor: pointer;
}

.hamNav > div {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
}

.hamNav > div div {
  display: block;
  width: 30px;
  height: 4px;
  margin: 2px;
  background-color: #593202;
  border-radius: 3px;
}

@media screen and (max-width: 650px) {
  .hamNav {
    left: auto;
    right: 0;
    top: 0;
    margin-left: 0;
    margin-top: 0;
  }
}
@media screen and (max-height: 500px) {
  .hamNav {
    left: auto;
    right: 0;
    top: 0;
    margin-left: 0;
    margin-top: 0;
  }
}

.buttons {
  padding: 10px 20px;
  width: 150px;
  border-radius: 16px;
  background-color: #d9a404;
}

.buttons:hover {
  background-color: #f2c438;
}
</style>
