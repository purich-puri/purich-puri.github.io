<template>
  <div id="nav">
    <router-link to="/">GO BACK</router-link>
  </div>
  <div class="hamNav" @click="showModal = true">
    <div>
      <div></div>
      <div></div>
      <div></div>
    </div>
  </div>

  <div v-if="showModal" class="modal-mask" @click="showModal = false">
    <div class="modal-container" @click.stop>
      <div class="modal-header">
        <div class="text-2xl p-2 font-semibold underline">
          ALL PROJECTS LIST
        </div>
      </div>
      <div class="modal-body">
        <div v-for="(project, index) in myProjects" :key="index">
          <div class="projects-list cursor-pointer" @click="projectId(index)">
            {{ project.name }}
          </div>
        </div>
        <div class="projects-list">
          <a href="https://github.com/purich-puri" target="_blank">
            More on Github
          </a>
        </div>
      </div>
    </div>
  </div>

  <div class="wrapper">
    <div class="sections">
      <div
        class="projectTitle block flex justify-center items-center text-4xl bg-y-1"
      >
        {{ myProjects[this.state.picker].name.toUpperCase() }}
      </div>
      <div class="block flex flex-wrap justify-center items-center bg-y-3 p-2">
        {{ myProjects[this.state.picker].description }}
      </div>

      <div class="block flex justify-center items-center bg-y-4">
        <div class="img-container flex justify-center">
          <div
            v-if="myProjects[this.state.picker].img.length >= 1"
            class="white-img img-arrow cursor-pointer"
            @click="preImg"
          >
            <img src="../assets/double-left-48.png" alt="" />
          </div>
          <img
            class="img-display"
            :src="myProjects[this.state.picker].img[this.state.imgId]"
            alt=""
          />
          <div
            v-if="myProjects[this.state.picker].img.length >= 1"
            class="white-img img-arrow cursor-pointer"
            @click="nextImg"
          >
            <img src="../assets/double-right-48.png" alt="" />
          </div>
        </div>
      </div>

      <div class="block flex justify-center items-center bg-y-5">
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
      this.showModal = false;
      this.state.imgId = 0;
    },
    goToLink(link) {
      window.open(link);
    },
    preImg() {
      if (this.state.imgId !== 0) {
        this.state.imgId--;
      }
    },
    nextImg() {
      let imgLength = this.myProjects[this.state.picker].img.length - 1;

      if (this.state.imgId < imgLength) {
        this.state.imgId++;
      }
    },
  },
  data() {
    const state = reactive({
      picker: 0,
      imgId: 0,
    });

    return {
      showModal: false,
      state,
      myProjects: [
        {
          name: "Pokemon App",
          description:
            "A pokemon database that display all generation 1 pokemons wiith each individuals information.",
          liveLink: "https://purich-puri.github.io/pokemon-app/",
          repo: "https://github.com/purich-puri/pokemon-app",
          img: [
            require("../assets/pkmnApp/pkmn-img-1.png"),
            require("../assets/pkmnApp/pkmn-img-2.png"),
          ],
        },
        {
          name: "Tracker App",
          description:
            "A reminder app for learning Vue3 fundamentals from passing props to returning emits.",
          liveLink: "",
          repo: "https://github.com/purich-puri/tracker-app",
          img: "",
        },
        {
          name: "Get Random User",
          description:
            "A mini project that simple retrieve a random user data from a public api called 'randomuser.me'",
          liveLink: "",
          repo: "https://github.com/purich-puri/get-random-user",
          img: "",
        },
        {
          name: "Library",
          description: "A small library site to learn the fundamental of CRUD",
          liveLink: "https://purich-puri.github.io/odin-library/",
          repo: "https://github.com/purich-puri/odin-library",
          img: "",
        },
        {
          name: "Calculator",
          description: "A Calculator app using pure JS.",
          liveLink: "https://purich-puri.github.io/odin-calculator/",
          repo: "https://github.com/purich-puri/odin-calculator/",
          img: [require("../assets/calculator.png")],
        },
        {
          name: "Rock Paper Scissor",
          description: "A Rock Paper Scissor game using pure JS",
          liveLink: "https://purich-puri.github.io/odin-rps/",
          repo: "https://github.com/purich-puri/odin-rps/",
          img: "",
        },
        {
          name: "Pocket Planner",
          description:
            "A mobile application using Ionic & Cordova to create a trip planner by using google direction api, then displaying the direction visually with google map api and then storing these data on a server with google firebase.",
          liveLink: "",
          repo: "https://github.com/purich-puri/PocketPlanner",
          img: [
            require("../assets/pocketPlanner/pp-1.png"),
            require("../assets/pocketPlanner/pp-2.png"),
            require("../assets/pocketPlanner/pp-3.gif"),
          ],
        },
        {
          name: "Get Invited",
          description:
            "A mobile group chat application using Ionic, Cordova & Firebase",
          liveLink: "",
          repo: "https://github.com/purich-puri/getInvited",
          img: [
            require("../assets/getInvited/gi-1.png"),
            require("../assets/getInvited/gi-2.png"),
            require("../assets/getInvited/gi-3.png"),
            require("../assets/getInvited/gi-4.png"),
          ],
        },
        {
          name: "Math It",
          description:
            "Created with Unity to create a 3D math game that helps visualize the concepts of basic arithmetic for  target audience (kids aged 5 - 12).",
          liveLink: "",
          repo: "https://github.com/purich-puri/Math-It",
          img: [require("../assets/mathIt/math-it-img.gif")],
        },
        {
          name: "My Password Storage",
          description:
            "Generate or Store a password in one iOS application purely written in objC",
          liveLink: "",
          repo: "https://github.com/purich-puri/MyPasswordStorage",
          img: "",
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
  left: 20px;
  padding: 0 10px;
  top: 0;
  color: #fff;
  background-color: #d9a404;
  border-radius: 5px 5px 0 0;
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

.modal-mask {
  position: fixed;
  z-index: 1;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal-container {
  width: 300px;
  margin: 0px auto;
  padding: 20px 30px;
  background-color: #d9a404;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
}

.img-container {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.img-display {
  max-width: 80%;
  max-height: 80%;
}

.img-arrow {
  display: flex;
  align-items: center;
  justify-content: center;
}

.projects-list:hover {
  background-color: #8c5c03;
  border-radius: 16px;
}

@media screen and (max-width: 650px) {
  .hamNav {
    left: auto;
    right: 0;
    top: 0;
    margin-left: 0;
    margin-top: 0;
  }

  .modal-mask {
    height: 100%;
  }

  .modal-container {
    height: 100%;
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
