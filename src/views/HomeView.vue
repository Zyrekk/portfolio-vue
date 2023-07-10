<template>
  <section class="home">
    <WelcomeComponent/>
    <MyValuesComponent/>
    <ProjectsContainer/>
  </section>
</template>

<script>

import WelcomeComponent from "@/components/WelcomeComponent.vue";
import MyValuesComponent from "@/components/MyValuesComponent.vue";
import ProjectsContainer from "@/components/ProjectsContainer.vue";

export default {
  name: 'HomeView',
  components:{
    WelcomeComponent,
    MyValuesComponent,
    ProjectsContainer,
  }
}
</script>

<style>
.home{
  box-sizing: border-box;
  margin-top: 10rem;
  width: 100%;
}
@media screen and (max-width: 900px) {
  .home{
    margin-top: 3rem;
  }
}
</style>
