<template>
  <div class="project">
    <a v-bind:href="project.link" class="project__link">{{ project.name }}</a>
    <p class="project__description">{{ project.description }}</p>
  </div>
</template>

<script>
export default {
  name: "Project",

  props: {
    project: {
      type: Object,
      required: true
    }
  }
};
</script>

<style lang="scss">
.project {
  max-width: 600px;
  width: 100%;
  box-shadow: 2px 5px 10px rgba(0, 0, 0, 0.3);
  background-color: white;
  margin: 1rem auto;
  text-indent: 8px;
  border: 2px solid hsl(200, 60%, 70%);
  border-radius: 0.4rem;
  padding: 0.7rem 1rem;
  line-height: 1.4;

  .project__link:link,
  .project__link:visited {
    font-size: 1.2rem;
    color: hsl(200, 40%, 40%);
    text-decoration: none;
  }

  .project__link:hover,
  .project__link:active {
    color: hsl(200, 40%, 30%);
    cursor: pointer;
  }
}
</style>
