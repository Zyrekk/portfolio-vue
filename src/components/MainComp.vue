<template>
  <div class="MainContainer">
    <div class="TilesContainer">
      <div class="Box">
        <h3>About me</h3>
        <div class="BoxContent">
                        <span>
                            I am a third year IT student. Frontend interested me more about 7 months ago after classes
                        conducted by Allegro employees. I am determined and I am working towards the goal I have set for
                        myself. My motto is never give up.
                        </span>
        </div>
      </div>
      <div class="Box">
        <h3>Education</h3>
        <div class="BoxContent">
          <div class="EducationTile">
            <div class="EducationContent">
              <div class="EduPlace">
                <span>Nicolaus Copernicus University in Torun</span>
                <div class="Period">2019 - up</div>
              </div>
              <span>IT - engineering studies</span>
            </div>
            <div class="EducationContent">
              <div class="EduPlace">
                <span>I High School in Malbork</span>
                <div class="Period">2016 - 2019</div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="Box">
        <h3>Experience</h3>
        <div class="BoxContent">
          <div class="ExperienceTile">
            <div class="ExperienceContent">
              <div class="Place">
                <span>JustResearch project</span>
                <div class="Period">09.2022 - up</div>
              </div>
              <span>I am a member of a team that creates a web application for students who conduct research and need large and specific data</span>
            </div>
            <div class="ExperienceContent">
              <div class="Place">
                <span>UMK Allegro classes</span>
                <div class="Period">10.2022 - up</div>
              </div>
              <span>I took additional classes taught by allegro staff, with whom we developed our first web applications</span>
            </div>
          </div>
        </div>
      </div>
      <div class="Box">
        <h3>Competencies</h3>
        <div class="CompetenciesContent">
          <div class="CompetenciesTile">
            <span>HTML</span>
            <font-awesome-icon :icon="['fab', 'html5']" size="3x" />
              <span>11 months</span>
          </div>
          <div class="CompetenciesTile">
            <span>CSS</span>
            <font-awesome-icon :icon="['fab', 'css3-alt']" size="3x" />
              <span>10 months</span>
          </div>
          <div class="CompetenciesTile">
            <span>JAVASCRIPT</span>
            <font-awesome-icon :icon="['fab', 'square-js']" size="3x" />
              <span>8 months</span>
          </div>
          <div class="CompetenciesTile">
            <span>REACT.JS</span>
            <font-awesome-icon :icon="['fab', 'react']" size="3x" />
              <span>5 months</span>
          </div>
          <div class="CompetenciesTile">
            <span>VUE.JS</span>
            <font-awesome-icon :icon="['fab', 'vuejs']" size="3x" />
              <span>1 month</span>
          </div>

          <div class="CompetenciesTile">
            <span>JAVA</span>
            <font-awesome-icon :icon="['fab', 'java']" size="3x" />
              <span>15 months</span>
          </div>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
import { library } from '@fortawesome/fontawesome-svg-core'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faJava,faVuejs,faReact,faSquareJs,faCss3Alt,faHtml5} from '@fortawesome/free-brands-svg-icons'
library.add(faJava,faVuejs,faReact,faSquareJs,faCss3Alt,faHtml5)
export default {
  name: "MainComp",
  components: {
    FontAwesomeIcon
  },
}
</script>

<style scoped>


.MainContainer {
  color: white;
  margin-top: 6rem;
  display: flex;
  justify-content: center;
  align-items: center;
}

.TilesContainer {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 4rem;
  width: 100%;
  height: max-content;
  padding: 50px 0;
}

.Box {
  padding: 15px;
  display: flex;
  flex-direction: column;
  max-width: 40rem;
  width: 40%;
  border-radius: 20px;
  border: 3px solid rgba(255, 255, 255, .3);
}

.Box h3 {
  position: relative;
  width: fit-content;
  margin-top: 0;
}

.Box h3::after {
  left: 0;
  bottom: 0;
  position: absolute;
  content: '';
  width: 100%;
  border: 1px solid white;
  border-radius: 20px;
}


.BoxContent {
  min-height: 7rem;
  height: 100%;
}

.BoxContent span {
  line-height: 30px;
}

.CompetenciesContent {
  width: 100%;
  margin: 0 auto;
  display: flex;
  gap: 3rem;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}

.CompetenciesTile {
  width: 8rem;
  display: flex;
  min-height: 7rem;
  flex-wrap: wrap;
  gap: 10px;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.ExperienceTile {
  display: flex;
  flex-direction: column;
  gap: 2rem

}

.ExperienceContent:last-child:after {
  height: 0;

}

.ExperienceContent {
  position: relative;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.ExperienceContent::after {
  content: '';
  position: absolute;
  width: 100%;
  height: 3px;
  bottom: -10px;
  background: rgba(255, 255, 255, .3);
}

.Place {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
}

.Place span {
  font-size: 18px;
  font-style: italic;
  font-weight: bold;
  box-sizing: border-box;
  padding: 5px 0;
}

.Period {
  box-sizing: border-box;
  border-radius: 20px;
  background-color: rgba(255, 255, 255, .3);
  padding: 5px 10px 2px;
}

.EducationTile {
  display: flex;
  flex-direction: column;
  gap: 2rem
}

.EducationContent {
  position: relative;
  display: flex;
  flex-direction: column;
}

.EducationContent::after {
  content: '';
  position: absolute;
  width: 100%;
  height: 3px;
  bottom: -10px;
  background: rgba(255, 255, 255, .3);
}

.EducationContent:last-child:after {
  height: 0;
}

.EduPlace {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
}

.EduPlace span {
  font-style: italic;
  font-weight: bold;
  box-sizing: border-box;
  padding: 5px 0;
}


</style>