<template>
  <NavigationComponent/>
  <router-view/>
</template>

<script>
import NavigationComponent from "@/components/NavigationComponent.vue";
export default {
  name:"App",
  components:{NavigationComponent}

}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,100;0,300;0,400;0,700;0,900;1,100;1,300;1,400;1,700;1,900&display=swap');

body{
  margin: 0;
  padding: 0;

}
#app {
  font-family: 'Lato', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background: #0f172a;
  color: white;
  min-height: 100vh;
  overflow-y: hidden;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
