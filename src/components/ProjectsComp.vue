<template>
  <div class="ProjectsMainContainer">
    <div class="ProjectSectionTitle">Projects</div>
    <div class="ProjectsContainer">
      <section class="Project">
        <img :src="netflix" alt="netflix dashboard view image"/>
        <h4>Netflix - Dashboard view</h4>
        <div>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ipsa, qui.</div>
      </section>
      <section class="Project">
        <img :src="spotify" alt="spotify dashboard view image"/>
        <h4>Spotify - Playlist view</h4>
        <div>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ipsa, qui.</div>
      </section>
      <section class="Project">
        <img :src="spotifyLogin" alt="spotify login view image"/>
        <h4>Spotify - Login & register view</h4>
        <div>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ipsa, qui.</div>
      </section>
    </div>
  </div>

</template>

<script>
export default {
  name: "ProjectsComp",
  data() {
    return {
      netflix: require('./../assets/netflix.png'),
      spotify: require('./../assets/spotify.png'),
      spotifyLogin: require('./../assets/spotifyLogin.png')
    }
  }
}
</script>

<style scoped>

.ProjectsMainContainer {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  color: white;
}

.ProjectSectionTitle {
  margin-top: 2rem;;
  font-size: 2rem;
}

.ProjectsContainer {
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
  padding: 15px;
  display: flex;
  flex-direction: column;
  width: 19rem;
  border-radius: 10px;
}

.Project img {
  border-radius: 10px;
  width: 100%;
  margin: 0 auto;

}


</style>