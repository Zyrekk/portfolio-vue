<template>
  <section class="contact">
    <div class="contact__alert" :class="{'contact__alert--visible':isClickedEmailText}">Copied to clipboard</div>
    <h3>
      <span class="contact__text">your</span>
      <span class="contact__text">contact me</span>
    </h3>
    <div class="contact__options-wrapper">
      <a class="contact__link" href="https://discord.gg/nPCZaZbg2S" rel="noreferrer" target="_blank">
        <div class="contact__option">
          <font-awesome-icon class="contact__icon" :icon="['fab', 'discord']" size="2x"/>
          <p>Discord</p>
        </div>
      </a>
      <a class="contact__link" href="https://www.linkedin.com/in/konrad-żyra-a8131226a/" rel="noreferrer"
         target="_blank">
        <div class="contact__option">
          <font-awesome-icon class="contact__icon" :icon="['fab', 'linkedin']" size="2x"/>
          <p>Linkedin</p>
        </div>
      </a>
      <a class="contact__link" href="mailto:zyrekk.dev@gmail.com" rel="noreferrer"
         target="_blank">
        <div class="contact__option">
          <font-awesome-icon class="contact__icon" :icon="['fas', 'envelope']" size="2x"/>
          <p>E-mail</p>
        </div>
      </a>
      <div class="contact__option" @click="copyEmail">
        <p>{{email}}</p>
      </div>
    </div>
  </section>
</template>

<script>
import {library} from '@fortawesome/fontawesome-svg-core'
import {FontAwesomeIcon} from '@fortawesome/vue-fontawesome'
import {faDiscord, faLinkedin} from '@fortawesome/free-brands-svg-icons'
import {faEnvelope} from '@fortawesome/free-solid-svg-icons'
import {ref} from "vue";

library.add(faDiscord, faLinkedin, faEnvelope)
export default {
  name: "ContactContainer",
  components: {
    FontAwesomeIcon
  },
  setup(){
    const email='zyrekk.dev@gmail.com'
    const isClickedEmailText=ref(false);
    const  copyEmail=() =>{
      isClickedEmailText.value=true
      navigator.clipboard.writeText(email)
      setTimeout(()=>{
        isClickedEmailText.value=false
      },2000)
    }
    return{email,isClickedEmailText,copyEmail}
  }
}
</script>

<style lang="scss" scoped>

.contact {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-direction: column;
  max-width: min(1440px, 90vw);
  margin-top: 12rem;
  width: 100%;
}

.contact__alert{
  transition: .5s ease-in-out;
  position: fixed;
  z-index: 100;
  top: 0;
  padding: 1rem;
  border-radius: 20px;
  left: 50%;
  transform: translateX(-50%);
  font-size: 1.1rem;
  opacity: 0;
  background: #818cf8;
}

.contact__alert--visible{
  opacity: 1;
  top: 3rem;
}

h3 {
  animation: scale 2s;
}

.contact__link {
  all: unset;
  cursor: pointer;
  display: flex;
  justify-content: center;
}

.contact__text {
  font-size: 2rem;
  color: #818cf8;

  &:before {
    content: "Choose ";
    color: #fff;
  }

  &:after {
    content: " way to ";
    color: #fff;
  }

  &:last-child {
    &:after {
      content: '';
    }

    &:before {
      content: '';
    }
  }
}

.contact__options-wrapper {
  flex-wrap: wrap;
  margin-top: 10rem;
  display: flex;
  justify-content: center;
  gap: 2rem;
  align-items: center;
  margin-bottom: 9.1rem;
}

.contact__icon {
  transition: .2s ease-in-out;
  transform: rotateY(0deg);
}

.contact__option {
  animation: scale 2s;
  border-radius: 50px;
  border: 2px solid #818cf8;
  padding: 0 25px;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 0.3rem;
  cursor: pointer;
  transition: .2s ease-in-out;

  &:hover {
    background: #818cf8;
    transform: translateY(-5px);
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

@media screen and (max-width: 490px) {
  .contact__options-wrapper {
    width: 100%;
    flex-direction: column;
    margin-top: 3rem;
  }
  .contact__link{
    width: 100%;
  }
  .contact__option {
    justify-content: space-evenly;
    width: 80%;
    &:last-child {
      padding: 0;
    }
  }
  .contact {
    margin-top: 4rem;
  }
}

@media screen and (max-width: 490px) {
  .contact {
    margin-top: 2rem;
  }
}

</style>
