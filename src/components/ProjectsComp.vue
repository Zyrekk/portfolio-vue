<template>
  <div class="ProjectsMainContainer">
    <span class="ProjectSectionTitle">Projects</span>
    <div class="ProjectsContainer">
      <section ref="portfolioProjectRef" class="Project" :class="{'invisible':!visibility.portfolioProject}">
        <a href="https://github.com/Zyrekk/portfolio-vue" target="_blank" class="Link">
          <img :src="portfolio" alt="portfolio website image"/>
        </a>
        <h4>Portfolio - Website</h4>
        <div>Portfolio website to learn the vue framework</div>
        <div class="ProjectButtons">
          <a :class="{'light':!darkMode}" href="https://github.com/Zyrekk/portfolio-vue" target="_blank" class="Link">
            <p>GitHub</p>
          </a>
        </div>
      </section>
      <section ref="spotifyLoginProjectRef" class="Project" :class="{'invisible':!visibility.spotifyLoginProject}">
        <a href="https://konradzyra-spotify-login.netlify.app" target="_blank" class="Link">
          <img :src="spotifyLogin" alt="spotify login view image"/>
        </a>
        <h4>Spotify - Login & register view</h4>
        <div>Simple spotify login and register form with data validation</div>
        <div class="ProjectButtons">
          <a :class="{'light':!darkMode}" href="https://github.com/Zyrekk/spotify-login-app" target="_blank" class="Link">
            <p>GitHub</p>
          </a>
          <a :class="{'light':!darkMode}" href="https://konradzyra-spotify-login.netlify.app" target="_blank" class="Link">
            <p>Live demo</p>
          </a>
        </div>
      </section>
      <section ref="weatherProjectRef" class="Project" :class="{'invisible':!visibility.weatherProject}">
        <a href="https://konradzyra-weather.netlify.app" target="_blank" class="Link">
          <img :src="weather" alt="weather application"/>
        </a>
        <h4>Weather app</h4>
        <div>Simple weather app made using openweather api</div>
        <div class="ProjectButtons">
          <a :class="{'light':!darkMode}" href="https://github.com/Zyrekk/weather-app-vue" target="_blank" class="Link">
            <p>GitHub</p>
          </a>
          <a :class="{'light':!darkMode}" href="https://konradzyra-weather.netlify.app" target="_blank" class="Link">
            <p>Live demo</p>
          </a>
        </div>
      </section>
      <section ref="spotifyPlayListProjectRef" class="Project" :class="{'invisible':!visibility.spotifyPlayListProject}">
        <a href="https://github.com/Zyrekk/spotify-home-view" target="_blank" class="Link">
          <img :src="spotify" alt="spotify dashboard view image"/>
        </a>
        <h4>Spotify - Home view - in progress...</h4>
        <div>Simple spotify home view clone, still in progress</div>
        <div class="ProjectButtons">
          <a :class="{'light':!darkMode}" href="https://github.com/Zyrekk/spotify-home-view" target="_blank" class="Link">
            <p>GitHub</p>
          </a>
        </div>
      </section>
    </div>
  </div>

</template>

<script>
import {onMounted, reactive, toRefs} from "vue";

export default {
  name: "ProjectsComp",
  props:["darkMode"],
  setup(){
    const visibility=reactive({
      portfolioProject:false,
      spotifyPlayListProject:false,
      spotifyLoginProject:false,
      weatherProject:false,
    })
    const refElements=reactive({
      portfolioProjectRef:null,
      spotifyPlayListProjectRef:null,
      spotifyLoginProjectRef:null,
      weatherProjectRef:null,
    })
    onMounted(() => {
      const portfolioProjectObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.intersectionRatio >= 0.5) {
            visibility.portfolioProject = true
          }
          else {
            visibility.portfolioProject = false
          }
        })
      }, {threshold: 0.5});
      portfolioProjectObserver.observe(refElements.portfolioProjectRef);

      const weatherProjectObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.intersectionRatio >= 0.5) {
            visibility.weatherProject = true
          }
          else {
            visibility.weatherProject = false
          }
        })
      }, {threshold: 0.5});
      weatherProjectObserver.observe(refElements.weatherProjectRef);

      const spotifyPlayListProjectObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.intersectionRatio >= 0.5) {
            visibility.spotifyPlayListProject = true
          }
          else {
            visibility.spotifyPlayListProject = false
          }
        })
      }, {threshold: 0.5});
      spotifyPlayListProjectObserver.observe(refElements.spotifyPlayListProjectRef);

      const SpotifyLoginProjectObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.intersectionRatio >= 0.5) {
            visibility.spotifyLoginProject = true
          }
          else {
            visibility.spotifyLoginProject = false
          }
        })
      }, {threshold: 0.5});
      SpotifyLoginProjectObserver.observe(refElements.spotifyLoginProjectRef);
    });

    return {...toRefs(refElements), visibility}
  },
  data() {
    return {
      portfolio: require('./../assets/portfolio.png'),
      spotify: require('./../assets/spotify.png'),
      spotifyLogin: require('./../assets/mySpotify.png'),
      weather: require('./../assets/weather.png')
    }
  },
}
</script>

<style scoped>

.ProjectsMainContainer {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.ProjectSectionTitle {
  z-index: 10;
  margin-top: 2rem;;
  font-size: 2rem;
}

.ProjectsContainer {
  z-index: 10;
  box-sizing: border-box;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 4rem;
  width: 100%;
  height: max-content;
  padding: 50px 27px;
}

.Project {
  z-index: 10;
  opacity: 1;
  padding: 15px;
  display: flex;
  flex-direction: column;
  width: 19rem;
  border-radius: 10px;
  transition: .7s ease;
}

.Project.invisible{
  opacity: 0;
}

.Project img {
  border-radius: 10px;
  width: 100%;
  aspect-ratio: 16/9;
  margin: 0 auto;
  transition: .3s;
  transform-origin: center;
  backface-visibility: hidden;
}

.Project img:hover{
  transform: scale(1.05);
}

.ProjectButtons{
  display: flex;
  gap:1rem;
}

.ProjectButtons a{
  all: unset;
  cursor: pointer;
  position: relative;
}

.Link p{
  margin: 1.33em 0 0 0;
}

.ProjectButtons a::after {
  position: absolute;
  content: "";
  width: 100%;
  bottom: -4px;
  border-bottom: 2px solid white;
  transition: .2s;
}

.ProjectButtons a.light::after {
  position: absolute;
  content: "";
  width: 100%;
  bottom: 0;
  border-bottom: 2px solid #000000;
  transition: .2s;
}
</style>