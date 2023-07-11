<template>
  <NavigationComponent/>
  <router-view/>
  <FooterContainer/>
</template>

<script>
import NavigationComponent from "@/components/Nav/NavigationComponent.vue";
import FooterContainer from "@/components/Footer/FooterContainer.vue";
export default {
  name:"App",
  components:{FooterContainer, NavigationComponent}

}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900;1,100;1,300;1,400;1,700;1,900&display=swap');

:root{
 $website-width: 1200px;
}

body{
  margin: 0;
  padding: 0;
}
#app {
  display: flex;
  flex-direction: column;
  font-family: 'Lato', sans-serif;
  align-items: center;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  background: #030712;
  position: relative;
  overflow: hidden;
  min-height: 100vh;
}
</style>
