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
        <div class="welcome__button-background"/>
        <div class="welcome__wave welcome__wave--1"/>
        <span class="welcome__contact-text" @click="handleContact">Contact me</span>
      </button>

    </div>
    <div class="welcome__carousel">
      <transition-group tag="a" :href="links[image%5]" target="_blank" rel="noreferrer" class="welcome__box-shadow" name="fade">
        <img v-for="i in [image%5]" :key='i' class="welcome_image" :src="images[i]"/>
      </transition-group>
      <transition-group tag="a" :href="links[(image+1)%5]" target="_blank" rel="noreferrer" class="welcome__box-shadow-second" name="fade">
        <img v-for="i in [(image+1)%5]" :key='i' class="welcome_image" :src="images[i]"/>
      </transition-group>
    </div>
  </section>
</template>
<script>
import {onMounted, ref} from "vue";
import {useRouter} from "vue-router";

export default {
  name: "WelcomeComponent",
  setup() {
    const router = useRouter()
    const image = ref(0)
    const images = [require('@/assets/parleto.png'), require('@/assets/thesis.png'), require('@/assets/justresearch.png'), require('@/assets/weather.png'), require('@/assets/mySpotify.png')]
    const links = ['https://github.com/Zyrekk/web-dev-parleto-app', 'https://github.com/Zyrekk/explore-the-world',
      'https://github.com/UMK-PZ2022-Zesp01/UMK-PZ2022-Researcher-frontend', 'https://github.com/Zyrekk/weather-app-vue', 'https://github.com/Zyrekk/spotify-login-app']

    const handleContact = () => {
      router.push('/contact')
    }

    const switchImage = () => {
      if (image.value === 4) {
        image.value = 0
      }
      image.value = image.value + 1
    }
    onMounted(() => {
      setInterval(switchImage, 7000)
    });
    return {image, images,links, handleContact}
  }
}
</script>

<style lang="scss" scoped>

.welcome {
  display: flex;
  flex-wrap: wrap;
  box-sizing: border-box;
  justify-content: space-between;
  margin: auto;
  max-width: min(1440px, 90vw);
  width: 100%;
}

.welcome__left {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.welcome__left-wrapper {
  display: flex;
  flex-wrap: wrap;
  animation: scale 2s;
  justify-content: flex-start;
  align-items: center;
  gap: 1rem;
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
}

.welcome__welcome-text {
  animation: scale 2s;
  box-sizing: border-box;
  max-width: 531.6px;
  text-align: left;
}

.welcome__carousel {
  animation: float 6s ease-in-out infinite;
  margin-right: 14rem;
  width: 400px;
  position: relative;
}

.welcome__box-shadow {
  cursor: pointer;
  animation: scale 2s;
  overflow: hidden;
  -webkit-box-shadow: 0px 0px 14px 5px rgba(75, 82, 140, 1);
  -moz-box-shadow: 0px 0px 14px 5px rgba(75, 82, 140, 1);
  box-shadow: 0px 0px 14px 5px rgba(75, 82, 140, 1);
  width: 100%;
  border-radius: 20px;
  display: flex;
  z-index: 15;
  aspect-ratio: 1/1;
  position: relative;

  &:after {
    position: absolute;
    content: '';
    width: 100%;
    height: 100%;
    z-index: 2;
    -webkit-box-shadow: inset 0px 0px 46px 16px rgb(53, 58, 100);
    -moz-box-shadow: inset 0px 0px 46px 16px rgb(53, 58, 100);
    box-shadow: inset 0px 0px 46px 16px rgb(53, 58, 100);
  }
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

.welcome__box-shadow-second {
  cursor: pointer;
  animation: scale 2s;
  position: absolute;
  -webkit-box-shadow: 0px 0px 14px 5px rgba(75, 82, 140, 1);
  -moz-box-shadow: 0px 0px 14px 5px rgba(75, 82, 140, 1);
  box-shadow: 0px 0px 14px 5px rgba(75, 82, 140, 1);
  width: 100%;
  border-radius: 20px;
  display: flex;
  aspect-ratio: 1/1;
  z-index: -1;
  bottom: 0;
  right: 0;
  transition: .2s ease-in-out;
  transform: translate(50%, 50%);

  &:after {
    position: absolute;
    border-radius: 20px;
    content: '';
    width: 100%;
    height: 100%;
    z-index: 2;
    -webkit-box-shadow: inset 0px 0px 46px 16px rgb(53, 58, 100);
    -moz-box-shadow: inset 0px 0px 46px 16px rgb(53, 58, 100);
    box-shadow: inset 0px 0px 46px 16px rgb(53, 58, 100);
  }
}

.welcome__contact-button {
  all: unset;
  animation: scale 2s;
  cursor: pointer;
  display: flex;
  margin-top: 4rem;
  padding: 1rem;
  border-radius: 30px;
  position: relative;
  box-sizing: border-box;
  overflow: hidden;
  transform-origin: center;
  backface-visibility: hidden;
  transition: all .2s ease-in-out;

  &:hover {
    background-size: revert;
    transform-origin: center;
    backface-visibility: hidden;
    transform: scale(1.05) translateY(-5px);

    .welcome__contact-text {
      transform-origin: center;
      backface-visibility: hidden;
      text-shadow: 0px 0px 13px rgba(66, 68, 90, 1);
    }
  }
}

.welcome__button-background {
  width: 100%;
  height: 100%;
  position: absolute;
  left: 0;
  top: 0;
  background: linear-gradient(315deg, rgb(113, 121, 190) 0%, rgb(72, 78, 140) 45%, rgb(48, 52, 89) 82%);
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
  opacity: 0.5;
  background-image: url("@/assets/Wave2.svg");
}

.welcome__wave--1 {
  animation: animate 35s linear infinite;
}

/*fade transition*/
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: scale(0.9);
}

.fade-enter-to,
.fade-leave-from {
  opacity: 1;
  transform: scale(1);
}

.fade-enter-active {
  transition: all 1s ease-in-out;
}

.fade-leave-active {
  transition: all 1s ease-in-out;
}

@keyframes scale {
  0% {
    scale: 1.2;
  }
  100% {
    scale: 1;
  }
}

@keyframes animate {
  0% {
    background-position-x: 0px;
  }
  100% {
    background-position-x: 1440px;
  }
}

@keyframes float {
  0% {
    //box-shadow: 0 5px 15px 0px rgba(3, 7, 18, 0.6);
    transform: translatey(0px);
  }
  50% {
    //box-shadow: 0 25px 15px 0px rgba(3, 7, 18, 0.2);
    transform: translatey(-15px);
  }
  100% {
    //box-shadow: 0 5px 15px 0px rgba(3, 7, 18, 0.6);
    transform: translatey(0px);
  }
}

@media screen and (max-width: 1530px) {
  .welcome__carousel {
    margin-left: 0;
  }
}

@media screen and (max-width: 1340px) {
  .welcome {
    flex-direction: column;
  }
  .welcome__carousel {
    padding-top: 5rem;
    margin: 0 15%;
  }
  .welcome__box-shadow, .welcome__box-shadow-second {
    width: 130%;
  }
  .welcome__box-shadow-second {
    transform: translate(70%, 50%);
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
}

@media screen and (max-width: 1000px) {
  .welcome__box-shadow, .welcome__box-shadow-second {
    width: 100%;
  }
  .welcome__box-shadow-second {
    transform: translate(70%, 50%);
  }

}

@media screen and (max-width: 950px) {
  .welcome__left-wrapper {
    flex-direction: column;
    justify-content: unset;
    align-items: unset;
    gap: 0;
  }
  .welcome__position-text {
    text-align: left;
    margin-bottom: 0;
  }
  .welcome__welcome-text {
    padding-top: 2rem;
    font-size: 1.05rem;
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
    margin-left: 8%;
    width: 55%;
  }

  .welcome__box-shadow, .welcome__box-shadow-second {
    width: 100%;
  }
  .welcome__box-shadow-second {
    transform: translate(50%, 50%);
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

  .welcome__contact-button {
    margin-left: 1rem;
    margin-top: 2rem;
  }

  .nav-container {
    max-width: 90vw;
  }
}

@media screen and (max-width: 335px) {
  .welcome__position-text-secondary, .welcome__position-text {
    font-size: 3rem;
  }

  .welcome__welcome-text {
    font-size: 0.9rem;
  }

  .welcome__contact-button {
    padding: 13px;
  }

  .welcome__contact-text {
    font-size: 0.9rem;
  }
}

</style>
