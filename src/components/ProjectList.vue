<template>
  <div>
    <div v-for="(project, index) in myProjects" :key="index">
      {{ project.name }}
    </div>
  </div>
</template>

<script>
export default {
  name: "ProjectList",

  data() {
    return {
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
