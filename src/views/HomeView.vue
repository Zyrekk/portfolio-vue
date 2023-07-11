<template>
  <section class="home">
    <WelcomeComponent/>
    <MyValuesComponent/>
    <ProjectsContainer/>
    <QuickAbout/>
  </section>
</template>

<script>

import WelcomeComponent from "@/components/Home/WelcomeComponent.vue";
import MyValuesComponent from "@/components/Home/MyValuesComponent.vue";
import ProjectsContainer from "@/components/Home/ProjectsContainer.vue";
import QuickAbout from "@/components/Home/QuickAbout.vue";

export default {
  name: 'HomeView',
  components:{
    WelcomeComponent,
    MyValuesComponent,
    ProjectsContainer,
    QuickAbout
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
