<template>
  <LightEffectComp :darkMode="state.darkMode"/>
  <div :class="state.darkMode ? 'darkMode' : 'lightMode'">
    <HeaderComp :handleDarkMode="handleDarkMode" :darkMode="state.darkMode"/>
    <MainComp :darkMode="state.darkMode"/>
    <ProjectsComp :darkMode="state.darkMode"/>
  </div>
</template>

<script>
import HeaderComp from "@/components/HeaderComp.vue";
import MainComp from "@/components/MainComp.vue";
import ProjectsComp from "@/components/ProjectsComp.vue";
import LightEffectComp from "@/components/LightEffectComp.vue";
import {reactive} from "vue";

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp,
    ProjectsComp,
    LightEffectComp
  },
  setup() {
    const state = reactive({
      darkMode: true,
    })
    console.log(state.darkMode)

    const handleDarkMode=()=>{
      state.darkMode=!state.darkMode
    }
    return{state,handleDarkMode}
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

.darkMode {
  background: black;
  background-size: cover;
  color: white;
}

.lightMode {
  background: #cde8c6;
  background-size: cover;
  color: black;
}
</style>
