<template>
  <div class="projects__page">
    <h1 class="projects__title">Projects Page</h1>

    <div class="pt-4 projects">
      <Project
        v-for="project of projects"
        v-bind:project="project"
        v-bind:key="project.id"
      />
    </div>
  </div>
</template>

<script>
import Project from "@/components/Project";

export default {
  name: "Projects",
  components: {
    Project
  },

  data() {
    return {
      projects: [
        {
          id: 1,
          name: "Ottergram",
          description: "Vue Application about otters.",
          link: "/projects/ottergram"
        },
        {
          id: 2,
          name: "App",
          description: "Vue Application",
          link: "https://github.com/Nematjon1"
        },
        {
          id: 3,
          name: "App",
          description: "Vue Application",
          link: "https://github.com/Nematjon1"
        }
      ]
    };
  }
};
</script>

<style>
.projects__page {
  margin: 6rem 0 0;
}

.projects__title {
  text-align: center;
}

.projects {
  display: flex;
  flex-flow: wrap;
}
</style>
