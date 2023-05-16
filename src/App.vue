<template>
  <LightEffectComp/>
  <div class="lightMode">
    <HeaderComp/>
    <MainComp/>
    <ProjectsComp/>
  </div>
</template>

<script>
import HeaderComp from "@/components/HeaderComp.vue";
import MainComp from "@/components/MainComp.vue";
import ProjectsComp from "@/components/ProjectsComp.vue";
import LightEffectComp from "@/components/LightEffectComp.vue";

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp,
    ProjectsComp,
    LightEffectComp
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
  min-height: 100vh;
  overflow-y: hidden;
}

.lightMode{
  background: black;
  background-size: cover;
  color: white;
}
.darkMode{
  background-size: cover;
  color: black;
}
</style>
