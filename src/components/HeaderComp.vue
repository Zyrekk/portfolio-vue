<template>
  <header class="HeaderContainer">
    <div class="LightEffect">
      <span class="Bar"></span>
      <span class="Light"></span>
      <span class="Light2"></span>
      <span class="Circle"></span>
    </div>
    <div class="Job">Junior Front-end Developer</div>
    <h1>Konrad Żyra</h1>
    <div class="HeaderInfoContent">
      <div class="InfoTile">
        <p>zyrakonrad09@gmail.com</p>
        <div class="SingleIcon">
          <font-awesome-icon :icon="['fas', 'envelope']" size="lg" />
        </div>
      </div>
      <div class="InfoTile">
        <p>604 102 666</p>
        <div class="SingleIcon">
          <font-awesome-icon :icon="['fas', 'phone']" size="lg" />
        </div>
      </div>
      <div class="InfoTile">
        <a href="https://pl.linkedin.com/in/konrad-żyra-a8131226a" target="_blank" class="Link">
          <p>Konrad Żyra</p>
        </a>
        <div class="SingleIcon">
          <font-awesome-icon :icon="['fab', 'linkedin-in']" size="lg"/>
        </div>
      </div>
      <div class="InfoTile">
        <a href="https://github.com/Zyrekk" target="_blank" class="Link">
          <p>GitHub</p>
        </a>
        <div class="SingleIcon">
          <font-awesome-icon :icon="['fab', 'github']" size="xl"/>
        </div>

      </div>
    </div>
  </header>

</template>

<script>
import {library} from '@fortawesome/fontawesome-svg-core'
import {FontAwesomeIcon} from '@fortawesome/vue-fontawesome'
import {faGithub,faLinkedinIn,} from '@fortawesome/free-brands-svg-icons'
import {faPhone,faEnvelope} from '@fortawesome/free-solid-svg-icons'

library.add(faGithub,faLinkedinIn,faPhone,faEnvelope)

export default {
  name: "HeaderComp",
  components: {
    FontAwesomeIcon
  },
}
</script>

<style scoped>
.HeaderContainer {
  position: relative;
  box-sizing: border-box;
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: max-content;
}

.LightEffect {
  margin-top: -20px;
  width: 100%;
  position: relative;
}

.Bar {
  position: absolute;
  left: 50%;
  transform: translate(-50%);
  bottom: -30px;
  width: 35%;
  height: 4px;
  /*background: linear-gradient(rgba(255,255,255,.3), rgba(255, 255, 255, .3));*/
  border-radius: 50%;

}

.Light {
  position: absolute;
  left: 50%;
  width: 50%;
  height: 20rem;
  background: rgba(85, 43, 215, 0.1);
  transform: translate(-50%) perspective(12em) rotateX(20deg);
  filter: blur(70px);
}

.Light2 {
  position: absolute;
  left: 50%;
  bottom: -550px;
  width: 18rem;
  height: 20rem;
  background: rgba(255, 255, 255, 0.3);
  transform: translate(-50%) perspective(5em) rotateX(160deg) scale(1, 0.6);
  box-shadow: 8px 8px 24px 0px rgba(255, 255, 255, 0.35);
  filter: blur(70px);
}

.Circle {
  position: absolute;
  left: 50%;
  min-width: 98vw;
  max-width: 99vw;
  height: 100rem;
  border-radius: 50%;
  background: rgba(85, 43, 215, 0.1);
  transform: translate(-50%);
  filter: blur(60px);
}

.HeaderInfoContent {
  max-width: 100vw;
  width: 80%;
  height: fit-content;
  gap: 4rem;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  padding-bottom: 20px;
}

.SingleIcon {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 40px;
  height: 40px;
  border: 2px solid #8d8d8d;
  border-radius: 50%;
}

.InfoTile {
  display: flex;
  flex-direction: row-reverse;
  justify-content: flex-end;
  align-items: center;
  gap: 15px;
  z-index: 10;
}

a {
  all: unset;
  cursor: pointer;
}

.Link {
  position: relative;
}

.Link::after {
  position: absolute;
  content: "";
  width: 0;
  bottom: -5px;
  border-bottom: 2px solid white;
  transition: .2s;
}

.Link:hover::after {
  width: 100%;
}

.HeaderContainer h1 {
  font-size: 60px;
  text-align: center;
  width: 100%;
  height: 50%;
  z-index: 10;
}

.Job {
  box-sizing: border-box;
  display: flex;
  align-items: center;
  border: 2px solid white;
  border-radius: 20px;
  text-align: center;
  padding: 5px 10px 2px;
  margin: 60px 0 0;
  z-index: 10;
}

p {
  margin: 0;
}

@media screen and (max-width: 860px) {
  .InfoTile {
    width: 15rem;
    flex-direction: column-reverse;
  }


}


</style>