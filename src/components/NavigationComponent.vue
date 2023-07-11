<template>
  <section class="nav-container">
    <div class="nav-container__wrapper">
      <a class="nav-container__dev-name" href="">zyrekk.dev</a>
      <button v-if="windowWidth<=900&&!isBurgerClicked" @click="handleBurgerClick" class="nav-container__button">
        <div class="nav-container__line"/>
        <div class="nav-container__line"/>
        <div class="nav-container__line"/>
      </button>
      <nav class="nav-container__content" :class="{'nav-container__content--active' : isBurgerClicked }">
        <ul class="nav-container__links" :class="{'nav-container__links--active' : isBurgerClicked }">
          <li v-if="windowWidth<=900" class="nav-container__single-link"
              :class="{'nav-container__single-link--active' : isBurgerClicked }" @click="handleBurgerClick">
            <font-awesome-icon :icon="['fas', 'xmark']" size="xl"/>
          </li>
          <li v-if="windowWidth<=900" class="nav-container__single-link">Home</li>
          <li class="nav-container__single-link">About</li>
          <li class="nav-container__single-link">GitHub</li>
          <li class="nav-container__single-link">Contact</li>
        </ul>
      </nav>
    </div>
  </section>
</template>

<script>
import {ref, onMounted, onUnmounted} from 'vue';
import {library} from '@fortawesome/fontawesome-svg-core'
import {FontAwesomeIcon} from '@fortawesome/vue-fontawesome'
import {faXmark} from '@fortawesome/free-solid-svg-icons'

library.add(faXmark)

export default {
  name: "App",
  components: {FontAwesomeIcon},
  setup() {
    const windowWidth = ref(window.innerWidth);
    const isBurgerClicked = ref(false);

    const handleResize = () => {
      windowWidth.value = window.innerWidth;
    };

    const handleBurgerClick = () => {
      isBurgerClicked.value = !isBurgerClicked.value;
    };

    onMounted(() => {
      window.addEventListener('resize', handleResize);
    });

    onUnmounted(() => {
      window.removeEventListener('resize', handleResize);
    });

    return {windowWidth, isBurgerClicked, handleBurgerClick, handleResize};
  }
}

</script>

<style lang="scss" scoped>

.nav-container {
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 4rem;
  width: 100%;
}

.nav-container__wrapper {
  display: flex;
  max-width: min(1440px, 90vw);
  align-items: center;
  justify-content: space-between;
  width: 100%;

}

.nav-container__dev-name {
  animation: scale 2s;
  text-decoration: none;
  color: white;
  display: flex;
  font-weight: 600;
  font-size: 1.875rem;
  line-height: 2.25rem;
  transition: 0.2s ease-in-out;
  height: fit-content;
  cursor: pointer;

  &:hover {
    color: #818cf8;
  }
}

.nav-container__content {
  animation: scale 2s;
  width: fit-content;
  display: flex;
  align-items: center;
  justify-content: end;
  z-index: 10;
}

.nav-container__button {
  all: unset;
  top: 10px;
  margin-right: 3.5rem;
  width: 2.2rem;
  gap: 6px;
  display: flex;
  flex-direction: column;
  cursor: pointer;
  transition: 0.2s ease-in-out;

  &:hover {
    .nav-container__line {
      background: #818cf8;
    }
  }
}

.nav-container__line {
  transition: 0.2s ease-in-out;
  width: 80%;
  height: 3px;
  background: white;
  border-radius: 10px;
}

.nav-container__links {
  list-style-type: none;
  display: flex;
  gap: 2.5rem;
}

.nav-container__single-link {
  height: fit-content;
  font-size: 1.25rem;
  line-height: 1.75rem;
  font-weight: 600;
  cursor: pointer;
  color: white;
  transition: .2s ease-in-out;

  &:hover {
    color: #818cf8;
  }
}

@keyframes opacity {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@keyframes scale {
  0% {
    scale: 1.2;
  }
  100% {
    scale: 1;
  }
}

@media screen and (max-width: 900px) {
  .nav-container {
    max-width: 90vw;
    justify-content: space-between;
    margin-top: 2rem;
  }

  .nav-container__links {
    display: flex;
    padding-left: 0;
    list-style: none;
    margin: 0;
    gap: 2rem;
    flex-direction: column;
  }

  .nav-container__content {
    position: fixed;
    display: flex;
    align-items: start;
    justify-content: center;
    padding: 0;
    height: 100vh;
    opacity: 1;
    top: 0;
    right: 0;
    width: 60%;
    transform: translateX(100%);
    transition: .2s ease-out;
  }

  .nav-container__content--active {
    -webkit-backdrop-filter: blur(25px);
    backdrop-filter: blur(25px);
    background-color: rgba(76, 83, 157, 0.6);
    box-shadow: 0 18px 50px -10px rgba(0, 0, 0, .5);
    transition: .2s ease-out;
    transform: translateX(0);
  }

  .nav-container__dev-name {
    padding: 20px;
  }

  .nav-container__button {
    margin: 0;
    padding: 20px;
  }
  .nav-container__links {
    width: 100%;
    gap: 0;
  }

  .nav-container__single-link {
    padding: 1rem 0;
    width: 100%;

    &:first-child {
      margin-bottom: 2rem;
    }

    &:hover {
      background: rgba(0, 0, 0, 0.75);
    }
  }
}
</style>
