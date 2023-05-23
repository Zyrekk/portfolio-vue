<template>
  <header class="HeaderContainer">
    <div class="featureOff" :class="{'On':state.isResized}" >
      <div class="mode" :class="{'On':state.isResized}">
        <input type="checkbox" id="toggle" checked>
        <label @click="handleDarkMode" for="toggle" class="toggleLabel">
          <img class="sun"
               src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADIAAAAyCAYAAAAeP4ixAAAACXBIWXMAAAsTAAALEwEAmpwYAAACZ0lEQVR4nO2Zy2oUQRSGP5IMjiFBFFtcqHtjXkFF3QhCFNGH0BBvG3EjrnSvT+DtQUyWwpgY8TJu3IluxAQvUUzLgX+gHGZGq7u6ugz9QcFQ03UufapPnzoNDQ0NdfMEeMoWINf478kbRxIjuYjsAtoRHWkBO6nAiS/ACpBFcCQDngGfgR0EZBuwLIOeezqzBCx6XJ9JRy6dFpmguApeAXtDK+BPHS8r0lG5M9GcGBb6Igmgn3aJrVuKTIq/DlA6BhwB7qo8eQ980O97wGFd47IH+CaZ0Zxw7+LuvrmjQMfJVMNGR866mKwQ0S3NDWBThlqavgTMAJMaM5rrbUu79jqJcUvGfQcuDNg6LvbfRWBDa26SCKd0d82JYx7rjsuZX8BJamYCeKM7a5HwZd5J5SarNs45KXPUdhrGOLAqGWepkccyYqGEjCuScZ8a6cqIgyVkHJKM1wHtYgp4NyL/WwHosq55W1eUaclYK2GHtyP9Veya5qcjO7JIYHoZy152RZmtYmsVfdgvU5xrkvGAGjkvI1aVSn2xNS8kw1J5bdjp7a0MsbLDlwWt7VZxEvTljIzZUNnxr5zQGitv5kiEO44z83/ZZuOKRK9ovE1CjDnO5Nr3V5WRpjRmNdd7JjblRJHSJigTOme4nHbe9qNGd8B2srZP9Ock0ynv44BTXUsZ6JGq2nUNayg81H/9BlvEPsU+6rrNh06g8rulhlweq/lQZcsmRt8sWt8pq9qZSTUUioTe94tV5jhjOrcTkP3Az8hN7BXgB7CPwByI/FmhLZ3JkNyHnqI0jqTGlonIUhVn7IaGBrz4DejQ596rineIAAAAAElFTkSuQmCC">
          <img class="moon"
               src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADIAAAAyCAYAAAAeP4ixAAAACXBIWXMAAAsTAAALEwEAmpwYAAAC00lEQVR4nO2YW4hNYRSAP4YZySWDxANF54FmvI3JzHA8KBLJA+LZJQ9qeKAmIpQo8SZ5cx+S2+SBmHkZjaQYuaZcSpHLIIxhzNFfa9dqd/aZfc7ZZ6yd/dXqTPtf//7X2v8/a61/QUJCQsL/zEhgOXAM+AA8AMYQI0YDO4AuIOOTOmLCOuBTFgec3AHKiMEuNPsMfw78kb+7gRkYZwLwWDngdmQ9sEw9O4RxxgKdyuBbwBQZuyDP3K6kMMxQoEM5cRmokDH3+02et2OcXcqJq0C5Gputxg5gmFnAbzH0RZb8sEY5shLDtImRfUB9lvHtypEGDO9GRuR0gM4+pVONUZrVbgRFo93KES+KmaJcRaPWHHqblCMmE2FaGbg2h95ipbcE4yF3ej/Zvk/09mKQE2LcZ2BQP7r3Rdf9muOaGPckhO5WtXs1GONeHmXHeBUYLmGMzjzrJ51PFmKIdjHqYUj9EcBrmfMWmIgRTopRP4DBIefMUXWZu7ePwwDb1FGpyvMK7M17ZiFJppVBjXnO3aiuvt+BJnV/CUul5LIbAcVqaCpUd+R2AfOX+ror7yQgNMhFLWjNNHAY+KLmXqRIjqiXzS1g/mR1DdbSAzwCrgPnJWe5KPkroCuzuVhHZqryoyNEhg+iThzqCTA0k0PczowiAvQXXRVBA2O1HJ02aSO5UP1Uwv0pYIN0LL013XGMhGnSq/K+TqmjUK06Yi8lP0VGo68Z575sKUhJUPDWWhD1Au5/45xawCW7qRGvUQ28UmvspEQMU40IJ++BeRG9ewXwVb37KCVmONCiFnRJ73gRd/WUhN+MkoMD1QAfAuxRmdvJT4lEtSHqMtcLWAScAXrVO7qlRzbg1KubYcZ35K4A+4EtEk6bpLnd6svYnrRIdPxnlEluuVtAouuVS9h8jFElFfNN4GOA8W+As1JUuvIlFlRKiHZhdZKv8Z2QkJCQQKz5C+d7G1gxTFsDAAAAAElFTkSuQmCC">
        </label>
      </div>
    </div>
    <span class="moreInfo" @click="handleResize">
            <svg :class="{'svg light':!state.isResized&&!darkMode,'svgResized light':state.isResized&&!darkMode,'svg ':!state.isResized&&darkMode,'svgResized ':state.isResized&&darkMode}" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path
                d="M24 22h-24l12-20z"/></svg>
    </span>
    <div :class="darkMode?'Job':'Job light'">Junior Front-end Developer</div>
    <h1>Konrad Żyra</h1>
    <div class="HeaderInfoContent">
      <div class="InfoTile">
        <p>zyrakonrad09@gmail.com</p>
        <div :class="darkMode?'SingleIcon':'SingleIcon light'">
          <font-awesome-icon :icon="['fas', 'envelope']" size="lg"/>
        </div>
      </div>
      <div class="InfoTile">
        <p>604 102 666</p>
        <div :class="darkMode?'SingleIcon':'SingleIcon light'">
          <font-awesome-icon :icon="['fas', 'phone']" size="lg"/>
        </div>
      </div>
      <div class="InfoTile">
        <a href="https://pl.linkedin.com/in/konrad-żyra-a8131226a" target="_blank" class="Link" :class="{'light':!darkMode}">
          <p>Konrad Żyra</p>
        </a>
        <div :class="darkMode?'SingleIcon':'SingleIcon light'">
          <font-awesome-icon :icon="['fab', 'linkedin-in']" size="lg"/>
        </div>
      </div>
      <div class="InfoTile">
        <a href="https://github.com/Zyrekk" target="_blank" class="Link" :class="{'light':!darkMode}">
          <p>GitHub</p>
        </a>
        <div :class="darkMode?'SingleIcon':'SingleIcon light'">
          <font-awesome-icon :icon="['fab', 'github']" size="xl"/>
        </div>
      </div>
    </div>
  </header>

</template>

<script>
import {library} from '@fortawesome/fontawesome-svg-core'
import {FontAwesomeIcon} from '@fortawesome/vue-fontawesome'
import {faGithub, faLinkedinIn,} from '@fortawesome/free-brands-svg-icons'
import {faPhone, faEnvelope, faSun, faMoon,} from '@fortawesome/free-solid-svg-icons'
import {reactive} from "vue";


library.add(faGithub, faLinkedinIn, faPhone, faEnvelope, faSun, faMoon)

export default {
  name: "HeaderComp",
  props: ['handleDarkMode','darkMode'],
  components: {
    FontAwesomeIcon,
  },
  setup(){
    const state =reactive({
      isResized:false,
      darkMode:true
    })

    const handleResize=()=>{
      state.isResized=!state.isResized
    }

    return{state,handleResize}
  },
}
</script>

<style scoped>
.HeaderContainer {
  position: relative;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: max-content;
}

.featureOff{
  box-sizing: border-box;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 0;
  border: 2px solid transparent;
  transition: .3s ease;
}

.featureOff.On{
  height: 100px;
}

.moreInfo{
  margin-top: 2rem;
  cursor: pointer;
}

.svg {
  transform: rotate(180deg) scale(0.5);
  filter: invert();
  transition: transform 0.5s ease, filter 0.5s ease;
  animation: mover .8s infinite alternate;
}

.svgResized {
  transform: scale(0.5);
  filter: invert();
  transition: transform 0.5s ease, filter 0.5s ease;
  animation: moverRevert .8s infinite alternate;
}

.svgResized.light,.svg.light{
  filter: none;
}

input {
  display: none;
}

.mode {
  opacity: 0;
  width: 6rem;
  font-size: 6px;
  display: flex;
  gap: 1rem;
  right: 5rem;
  align-items: center;
  justify-content: center;
  transition: .3s ease;
}

.mode.On{
  opacity: 1;
}

.toggleLabel {
  position: relative;
  width: 100%;
  -webkit-box-shadow: inset 7px 24px 100px -34px rgba(255, 255, 255, 1);
  -moz-box-shadow: inset 7px 24px 100px -34px rgba(255, 255, 255, 1);
  box-shadow: inset 7px 24px 100px -34px rgba(255, 255, 255, 1);
  height: 42px;
  display: flex;
  justify-content: space-around;
  align-items: center;
  border-radius: 25px;
  cursor: pointer;
}

.toggleLabel:after {
  position: absolute;
  content: '';
  top: 5px;
  left: 6px;
  height: 32px;
  width: 32px;
  background: #b7b6b6;
  border-radius: 50%;
  z-index: 5;
  transition: .3s ease;
}


input:checked + .toggleLabel:after {
  left: 91px;
  background: #868686;
  transform: translateX(-100%);
}

.toggleLabel:active:after {
  width: 30px;
}

.moon, .sun {
  position: absolute;
  scale: 0.55;
  z-index: 10;
  transition: .3s ease;
}

.sun {
  left: -3px;
}

.moon {
  left: 50px;
}

input:checked + .toggleLabel .moon {
filter: invert();
}
input:checked + .toggleLabel .sun {
  filter: invert();
}

input:checked + .toggleLabel{
  -webkit-box-shadow: inset 7px 24px 100px -34px rgba(0, 0, 0, 1);
  -moz-box-shadow: inset 7px 24px 100px -34px rgba(0, 0, 0, 1);
  box-shadow: inset 7px 24px 100px -34px rgba(0, 0, 0, 1);
}


.HeaderInfoContent {
  z-index: 10;
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
  border: 2px solid #ffffff;
  border-radius: 50%;
}

.SingleIcon.light{
  border: 2px solid #000000;
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

.Link.light::after{
  border-bottom: 2px solid #000000;
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

.Job.light{
  border: 2px solid black;
}

p {
  margin: 0;
}

@-webkit-keyframes mover {
  0% { transform: rotate(180deg) scale(0.5) translateY(0); }
  100% { transform: rotate(180deg) scale(0.5) translateY(-10px); }
}
@keyframes mover {
  0% { transform: rotate(180deg) scale(0.5) translateY(0); }
  100% { transform: rotate(180deg) scale(0.5) translateY(-10px); }
}

@-webkit-keyframes moverRevert {
  0% { transform: scale(0.5) translateY(0); }
  100% { transform: scale(0.5) translateY(-10px); }
}
@keyframes moverRevert {
  0% { transform: scale(0.5) translateY(0); }
  100% { transform: scale(0.5) translateY(-10px); }
}

@media screen and (max-width: 860px) {
  .InfoTile {
    width: 15rem;
    flex-direction: column-reverse;
  }
}


</style>