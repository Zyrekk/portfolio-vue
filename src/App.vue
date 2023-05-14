<template>
  <HeaderComp/>
  <MainComp/>
  <ProjectsComp/>
</template>

<script>
import HeaderComp from "@/components/HeaderComp.vue";
import MainComp from "@/components/MainComp.vue";
import ProjectsComp from "@/components/ProjectsComp.vue";

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp,
    ProjectsComp
  }
}
</script>

<style>
body {
  margin: 0;
  font-family: 'Axiforma', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#app {
  background: black;
  background-size: cover;
  min-height: 100vh;
  overflow-y: hidden;
}
</style>
