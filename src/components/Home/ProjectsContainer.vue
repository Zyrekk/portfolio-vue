<template>
  <section class="projects">
    <div class="projects__text-wrapper">
      <h3 class="projects__title">Selected projects</h3>
      <div class="projects__secondary-text-wrapper">
        <span class="projects__github">Check out my </span>
        <a class="projects__link" href="https://github.com/Zyrekk" rel="noreferrer" target="_blank">
        <span class="projects__github projects__github--color">GitHub </span>
        </a>
        <span class="projects__github">to see more</span>
      </div>
    </div>
    <ProjectCard :info="projects[0]"/>
    <ProjectCard :info="projects[1]"/>
    <ProjectCard :info="projects[2]"/>
  </section>
</template>

<script>
import ProjectCard from "@/components/Home/ProjectCard.vue";

export default {
  name: "ProjectsContainer",
  components: {
    ProjectCard
  },
  setup(){
    const projects=[
      {
        title:"Expense tracker",
        desc:"The application allows you to track and add expenses with a subdivision by category",
        tech:["Vue.js","Vuex","Vuetify 3","Material design"],
        link:"https://github.com/Zyrekk/web-dev-parleto-app"
      },
      {
        title:"JustResearch",
        desc:"JustResearch is a project for team programming course completion",
        tech:["React.js","Google Maps","Own Kotlin api"],
        link:"https://github.com/UMK-PZ2022-Zesp01/UMK-PZ2022-Researcher-frontend"
      },
      {
        title:"Explore the world",
        desc:"My engineering thesis in progress - Travel app offering many facilities for adventurous people",
        tech:["React native","Expo","TypeScript","Jest testing library"],
        link:"https://github.com/Zyrekk/explore-the-world"
      }
    ]

    return{projects}
  }
}
</script>

<style lang="scss" scoped>

.projects {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  margin: 6rem auto 0 auto;
  max-width: min(1440px,90vw);
  width: 100%;
  gap: 3rem;
}

.projects__text-wrapper{
  animation: scale 2s;
  flex: 0 0 100%;
  display: flex;
  flex-direction: column;
}


.projects__title {
  font-weight: 600;
  font-size: 1.5rem;
  text-align: center;
  margin-bottom: 0;
}
.projects__github{
  text-align: center;
  color: #acaec9;
  font-weight: 600;
}

.projects__github--color{
  color: #818cf8;
  transition: .2s;
  transform-origin: center;
  backface-visibility: hidden;
  cursor: pointer;
  &:hover{
    color: #3f50e7;
  }
}

.projects__link{
  all: unset;
}

@keyframes scale {
  0% {
    scale: 1.2;
  }
  100% {
    scale: 1;
  }
}


</style>
