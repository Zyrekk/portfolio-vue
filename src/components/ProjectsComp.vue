<template>
  <div class="ProjectsMainContainer">
    <span class="ProjectSectionTitle">Projects</span>
    <div class="ProjectsContainer">
      <section ref="netflixProjectRef" class="Project" :class="{'invisible':!visibility.netflixProject}">
        <img :src="netflix" alt="netflix dashboard view image"/>
        <h4>Netflix - Dashboard view</h4>
        <div>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ipsa, qui.</div>
        <div class="ProjectButtons">
          <a :class="{'light':!darkMode}" href="https://github.com/Zyrekk/spotify-login-app" target="_blank" class="Link">
            <p>GitHub</p>
          </a>
          <a :class="{'light':!darkMode}" href="https://konradzyra-spotify-login.netlify.app" target="_blank" class="Link">
            <p>Live demo</p>
          </a>
        </div>
      </section>
      <section ref="spotifyPlayListProjectRef" class="Project" :class="{'invisible':!visibility.spotifyPlayListProject}">
        <img :src="spotify" alt="spotify dashboard view image"/>
        <h4>Spotify - Playlist view</h4>
        <div>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ipsa, qui.</div>
        <div class="ProjectButtons">
          <a :class="{'light':!darkMode}" href="https://github.com/Zyrekk/spotify-login-app" target="_blank" class="Link">
            <p>GitHub</p>
          </a>
          <a :class="{'light':!darkMode}" href="https://konradzyra-spotify-login.netlify.app" target="_blank" class="Link">
            <p>Live demo</p>
          </a>
        </div>
      </section>
      <section ref="spotifyLoginProjectRef" class="Project" :class="{'invisible':!visibility.spotifyLoginProject}">
        <img :src="spotifyLogin" alt="spotify login view image"/>
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
      netflixProject:false,
      spotifyPlayListProject:false,
      spotifyLoginProject:false,
    })
    const refElements=reactive({
      netflixProjectRef:null,
      spotifyPlayListProjectRef:null,
      spotifyLoginProjectRef:null,
    })
    onMounted(() => {
      const netflixProjectObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.intersectionRatio >= 0.5) {
            visibility.netflixProject = true
          }
          else {
            visibility.netflixProject = false
          }
        })
      }, {threshold: 0.5});
      netflixProjectObserver.observe(refElements.netflixProjectRef);

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
      netflix: require('./../assets/netflix.png'),
      spotify: require('./../assets/spotify.png'),
      spotifyLogin: require('./../assets/mySpotify.png')
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
  bottom: 0;
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