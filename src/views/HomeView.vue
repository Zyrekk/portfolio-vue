<template>
  <section class="home">
    <WelcomeComponent/>
  </section>
</template>

<script>

import WelcomeComponent from "@/components/WelcomeComponent.vue";

export default {
  name: 'HomeView',
  components:{
    WelcomeComponent
  }
}
</script>

<style>
.home{
  box-sizing: border-box;
  margin-top: 10rem;
  width: 100%;
  /*border: 2px solid red;*/
}
@media screen and (max-width: 900px) {
  .home{
    margin-top: 3rem;
  }
}
</style>
