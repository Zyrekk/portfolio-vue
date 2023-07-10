<template>
  <div class="projects">
    <h3 class="projects__title">TITLE</h3>
    <ProjectCard/>
    <ProjectCard/>
    <ProjectCard/>
  </div>
</template>

<script>
import ProjectCard from "@/components/ProjectCard.vue";

export default {
  name: "ProjectsContainer",
  components: {
    ProjectCard
  }
}
</script>

<style lang="scss" scoped>

.projects {
  max-width: 90vw;
  margin: 8rem auto 0;
  display: flex;
  gap: 2rem;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: stretch;
  width: 100%;
}

.projects__title {
  flex: 0 0 100%;
  text-align: center;
}


</style>
