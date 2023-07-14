<template>
  <NavigationComponent/>
  <router-view v-slot="{ Component }">
    <transition name="route" mode="out-in">
      <component :is="Component"></component>
    </transition>
  </router-view>
  <FooterContainer/>
</template>

<script>
import NavigationComponent from "@/components/Nav/NavigationComponent.vue";
import FooterContainer from "@/components/Footer/FooterContainer.vue";
import {useRouter} from "vue-router";
import {ref, watch} from "vue";
export default {
  name:"App",
  components:{FooterContainer, NavigationComponent},
  setup() {
    const router = useRouter();
    const route = ref(router.currentRoute.value.path);
    watch(() => router.currentRoute.value.path, (newPath) => {
      route.value=newPath
    });

    return { route };
  },

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
  background: #030712;
}

/* width */
::-webkit-scrollbar {
  width: 10px;
}

/* Track */
::-webkit-scrollbar-track {
  background: #02050c;
}

/* Handle */
::-webkit-scrollbar-thumb {
  transition: .2s ease-in-out;
  background: #525aab;
  border-radius: 15px;
  &:hover{
    background: #818cf8;
  }
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

/* route transitions */
.route-enter-from {
  opacity: 0;
  transform: translateX(100px);
}

.route-enter-active {
  transition: all 0.3s ease-out;
}

.route-leave-to {
  opacity: 0;
  transform: translateX(-100px);
}

.route-leave-active {
  transition: all 0.3s ease-in;
}
</style>
