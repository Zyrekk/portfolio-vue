<template>
  <div :class="state.darkMode ? 'darkMode' : 'lightMode'">
    <HeaderComp :handleDarkMode="handleDarkMode" :darkMode="state.darkMode"/>
    <MainComp :darkMode="state.darkMode"/>
    <ProjectsComp :darkMode="state.darkMode"/>
    <ContactComp :darkMode="state.darkMode"/>
  </div>
</template>

<script>
import HeaderComp from "@/components/HeaderComp.vue";
import MainComp from "@/components/MainComp.vue";
import ProjectsComp from "@/components/ProjectsComp.vue";
import ContactComp from "@/components/ContactComp.vue";
import {reactive} from "vue";

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp,
    ProjectsComp,
    ContactComp,
  },
  setup() {
    const state = reactive({
      darkMode: true,
    })

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
  background: #000000 url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='100%25' height='100%25' viewBox='0 0 800 400'%3E%3Cdefs%3E%3CradialGradient id='a' cx='396' cy='281' r='514' gradientUnits='userSpaceOnUse'%3E%3Cstop offset='0' stop-color='%238B44DD'/%3E%3Cstop offset='1' stop-color='%23000000'/%3E%3C/radialGradient%3E%3ClinearGradient id='b' gradientUnits='userSpaceOnUse' x1='400' y1='148' x2='400' y2='333'%3E%3Cstop offset='0' stop-color='%23000000' stop-opacity='0'/%3E%3Cstop offset='1' stop-color='%23000000' stop-opacity='0.5'/%3E%3C/linearGradient%3E%3C/defs%3E%3Crect fill='url(%23a)' width='800' height='400'/%3E%3Cg fill-opacity='0.4'%3E%3Ccircle fill='url(%23b)' cx='267.5' cy='61' r='300'/%3E%3Ccircle fill='url(%23b)' cx='532.5' cy='61' r='300'/%3E%3Ccircle fill='url(%23b)' cx='400' cy='30' r='300'/%3E%3C/g%3E%3C/svg%3E") fixed;
  background-size: cover;
  color: white;
}

.lightMode {
  background: #FFFFFF url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='100%25' height='100%25' viewBox='0 0 800 400'%3E%3Cdefs%3E%3CradialGradient id='a' cx='396' cy='281' r='514' gradientUnits='userSpaceOnUse'%3E%3Cstop offset='0' stop-color='%238D77F7'/%3E%3Cstop offset='1' stop-color='%23FFFFFF'/%3E%3C/radialGradient%3E%3ClinearGradient id='b' gradientUnits='userSpaceOnUse' x1='400' y1='148' x2='400' y2='333'%3E%3Cstop offset='0' stop-color='%23FFFFFF' stop-opacity='0'/%3E%3Cstop offset='1' stop-color='%23FFFFFF' stop-opacity='0.5'/%3E%3C/linearGradient%3E%3C/defs%3E%3Crect fill='url(%23a)' width='800' height='400'/%3E%3Cg fill-opacity='0.4'%3E%3Ccircle fill='url(%23b)' cx='267.5' cy='61' r='300'/%3E%3Ccircle fill='url(%23b)' cx='532.5' cy='61' r='300'/%3E%3Ccircle fill='url(%23b)' cx='400' cy='30' r='300'/%3E%3C/g%3E%3C/svg%3E") fixed;
  background-size: cover;
  color: black;
}
</style>
