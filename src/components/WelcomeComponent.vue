<template>
  <section class="welcome">
    <div class="welcome__left">
      <div class="welcome__left-wrapper">
        <h2 class="welcome__position-text">Fronted</h2>
        <span class="welcome__position-text-secondary">developer</span>
      </div>
      <h3 class="welcome__welcome-text">I'm pleased to welcome you to my frontend world, where you can get to know me
        and my skills better
      </h3>
      <button class="welcome__contact-button">
        <div class="welcome__wave welcome__wave--1"/>
<!--        <div class="welcome__wave welcome__wave&#45;&#45;2"/>-->
<!--        <div class="welcome__wave welcome__wave&#45;&#45;3"/>-->
        <span class="welcome__contact-text">Contact me</span>
      </button>

    </div>
    <div class="welcome__carousel">
      <div class="welcome__box-shadow ">
        <img class="welcome_image" :src="images[image%4]"/>
        <img class="welcome_image welcome_image--hidden" :class="{'welcome_image--active':transition}"
             :src="images[(image+1)%4]"/>
      </div>
      <div class="welcome__box-shadow-second">
        <div class="welcome__box-shadow ">
          <img class="welcome_image" :src="images[(image+1)%4]"/>
          <img class="welcome_image welcome_image--hidden" :class="{'welcome_image--active':transition}"
               :src="images[(image+2)%4]"/>
        </div>
      </div>
    </div>
  </section>
  <div class="absolute"></div>

</template>
<script>
// import {library} from '@fortawesome/fontawesome-svg-core'
// import {FontAwesomeIcon} from '@fortawesome/vue-fontawesome'
// import {faArrowRight} from '@fortawesome/free-solid-svg-icons'
import {ref, watch} from "vue";

// library.add(faArrowRight)
export default {
  name: "WelcomeComponent",
  // components: {FontAwesomeIcon},
  setup() {
    const image = ref(0)
    const transition = ref(false)
    const switchImage = () => {
      transition.value = true
      setTimeout(() => {
        image.value = image.value + 1
        transition.value = false
      }, 1000)
    }
    switchImage()
    watch(image, () => {
      console.log('xd')
      setTimeout(() => {
        switchImage()
      }, 7000)
    })
    const images = [require('@/assets/weather.png'), require('@/assets/portfolio.png'), require('@/assets/mySpotify.png'), require('@/assets/parleto.png')]

    return {image, transition, images}
  }
}
</script>

<style lang="scss" scoped>

.welcome {
  display: flex;
  flex-wrap: wrap;
  box-sizing: border-box;
  max-width: 90vw;
  width: 100%;
}

.welcome__left {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 0 10rem;
}

.welcome__left-wrapper {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
  align-items: center;
}

.welcome__position-text {
  font-size: 4rem;
  background: -webkit-linear-gradient(20deg, #eee, #818cf8);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.welcome__position-text-secondary {
  all: unset;
  font-weight: 600;
  color: #818cf8;
  font-size: 4rem;
  padding-left: 1rem;
}

.welcome__welcome-text {
  box-sizing: border-box;
  max-width: 531.6px;
  text-align: left;
}

.welcome__carousel {
  animation: float 6s ease-in-out infinite;
  margin-left: 8rem;
  width: 25%;
  position: relative;
}

.welcome__box-shadow {
  overflow: hidden;
  -webkit-box-shadow: 0px 0px 46px 16px rgba(0, 0, 0, 1);
  -moz-box-shadow: 0px 0px 46px 16px rgba(0, 0, 0, 1);
  box-shadow: 0px 0px 46px 16px rgba(0, 0, 0, 1);
  width: 100%;
  border-radius: 20px;
  display: flex;
  z-index: 15;
  aspect-ratio: 1/1;
}

.welcome_image {
  max-width: 100%;
  max-height: 100%;
  position: absolute;
  border-radius: 20px;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.welcome_image--hidden {
  transform: scale(0.95);
  opacity: 0;
}

.welcome_image--active {
  transition: 1s ease-in-out;
  transform: scale(1);
  opacity: 1;
}

.welcome__box-shadow-second {
  border: 2px solid transparent;
  position: absolute;
  -webkit-box-shadow: 0px 0px 46px 16px rgba(0, 0, 0, 1);
  -moz-box-shadow: 0px 0px 46px 16px rgba(0, 0, 0, 1);
  box-shadow: 0px 0px 46px 16px rgba(0, 0, 0, 1);
  width: 100%;
  border-radius: 20px;
  display: flex;
  aspect-ratio: 1/1;
  z-index: -1;
  bottom: 0;
  right: 0;
  transition: .2s ease-in-out;
  transform: translate(50%, 50%);

  &:hover {
    border: 2px solid #818cf8;;
  }
}

.welcome__contact-button {
  all: unset;
  cursor: pointer;
  display: flex;
  margin-top: 4rem;
  padding: 1rem;
  background: -webkit-linear-gradient(20deg, #2f3359, #4c539d);
  border-radius: 30px;
  position: relative;
  overflow: hidden;
  transform-origin: center;
  backface-visibility: hidden;
  transition: all .2s ease-in-out;
  &:hover{
    background-size: revert;
    transform-origin: center;
    backface-visibility: hidden;
    .welcome__contact-text {
      transform: scale(1.05);
      transform-origin: center;
      backface-visibility: hidden;
    }
  }
}

.welcome__contact-text {
  transition: all .1s ease-in-out;
  font-weight: 700;
  padding: 0 0.5rem;
  font-size: 1.2rem;
  z-index: 10;
}

.welcome__wave {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 110%;
  height: 90%;
  background-image:url("@/assets/Wave.svg") ;
 }

.welcome__wave--1 {
  animation: animate 30s linear infinite;
}

.welcome__wave--2 {
  background: red;
}

.welcome__wave--3 {
}

@keyframes animate {
  0% {
    background-position-x: 200px;
  }
  100% {
    background-position-x: 900px;
  }

}

@keyframes float {
  0% {
    box-shadow: 0 5px 15px 0px rgba(3, 7, 18, 0.6);
    transform: translatey(0px);
  }
  50% {
    box-shadow: 0 25px 15px 0px rgba(3, 7, 18, 0.2);
    transform: translatey(-15px);
  }
  100% {
    box-shadow: 0 5px 15px 0px rgba(3, 7, 18, 0.6);
    transform: translatey(0px);
  }
}

@media screen and (max-width: 900px) {
  .welcome {
    justify-content: center;
    margin: 0 auto;
  }
  .welcome__left-wrapper {
    justify-content: center;
  }
  .welcome__left {
    padding: 0 0;
  }
  .welcome__position-text {
    padding-left: 1rem;
    width: 100%;
    text-align: left;
    margin-bottom: 0;
  }
  .welcome__position-text-secondary {
    padding-left: 1rem;
    text-align: left;
    width: 100%;
    margin-top: 0;
  }
  .welcome__welcome-text {
    padding-left: 1rem;
  }
  .welcome__carousel {
    margin-top: 3rem;
    margin-left: -6rem;
    width: 55%;
  }

}

</style>
