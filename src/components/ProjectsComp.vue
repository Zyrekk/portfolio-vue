<template>
  <div class="ProjectsMainContainer">
    <div class="ProjectSectionTitle">Projects</div>
    <div class="ProjectsContainer">
      <section class="Project">
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
      <section class="Project">
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
      <section class="Project">
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
export default {
  name: "ProjectsComp",
  props:["darkMode"],
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
  padding: 15px;
  display: flex;
  flex-direction: column;
  width: 19rem;
  border-radius: 10px;
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