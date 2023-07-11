<template>
  <section class="about">
    <div class="about__info">
      <div class="about__image"/>
      <div class="about__wrapper">
        <h3 class="about__name">Konrad</h3>
        <p class="about__position">Frontend developer</p>
        <p class="about__time">1 year, 3 months</p>
      </div>
    </div>
    <div class="about__grid">
      <div class="about__card">
        <div class="about__grid-title">
          Skills
        </div>
        <div class="about__div-wrapper">
          <p class="about__technology">JavaScript</p>
          <p class="about__technology">TypeScript</p>
          <p class="about__technology">Vue.js</p>
          <p class="about__technology">React.js</p>
          <p class="about__technology">HTML+CSS</p>
          <p class="about__technology">GitHub</p>
          <p class="about__technology">RWD</p>
          <p class="about__technology">MongoDB</p>
        </div>
      </div>
      <div class="about__card">
        <div class="about__grid-title">
          About me
        </div>
        <p class="about__about-name">Hello, my name is Konrad.</p>
        <p class="about__about-desc">I am a fourth-year computer science student</p>
        <p class="about__about-desc">I have spent a great deal of time coding over the past few years. Through
          consistent daily coding practice, I
          have constantly improved my skills and expanded my knowledge of different programming languages and
          frameworks.
        </p>
        <p class="about__about-desc">I also have two years' experience with the backend, i.e. java kotlin spring etc, so
          you could say
          I am also a bit of a fullstack developer.
        </p>
      </div>
      <div class="about__card">
        <div class="about__grid-title">
          Coding since:
        </div>
        <div class="about__div-wrapper">
          <div class="about__since-wrapper">
            <p class="about__tech-name">JavaScript</p>
            <p class="about__tech-time">1 year, 1 month</p>
          </div>
          <div class="about__since-wrapper">
            <p class="about__tech-name">TypeScript</p>
            <p class="about__tech-time">2 months</p>
          </div>
          <div class="about__since-wrapper">
            <p class="about__tech-name">Vue.js</p>
            <p class="about__tech-time">4 months</p>
          </div>
          <div class="about__since-wrapper">
            <p class="about__tech-name">React.js</p>
            <p class="about__tech-time">9 months</p>
          </div>
          <div class="about__since-wrapper">
            <p class="about__tech-name">HTML+CSS</p>
            <p class="about__tech-time">1 year, 3 months</p>
          </div>
          <div class="about__since-wrapper">
            <p class="about__tech-name">GitHub</p>
            <p class="about__tech-time">1 year, 1 month</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AboutContainer"
}
</script>

<style lang="scss" scoped>

.about {
  display: flex;
  justify-content: center;
  flex-direction: column;
  max-width: min(1440px, 90vw);
  width: 100%;
}

.about__info {
  animation: scale 2s;
  margin: 7rem auto 0 auto;
  -webkit-box-shadow: 0px 0px 24px 0px rgba(14, 23, 49, 0.62);
  -moz-box-shadow: 0px 0px 24px 0px rgba(14, 23, 49, 0.62);
  box-shadow: 0px 0px 24px 0px rgba(14, 23, 49, 0.62);
  background: -webkit-linear-gradient(45deg, rgba(11, 21, 49, 0.62), rgba(39, 48, 87, 0.62));
  display: flex;
  padding: 1rem;
  border-radius: 80px;
  align-items: center;
  width: 80%;
}

.about__image {
  object-fit: contain;
  width: 100px;
  height: 100px;
  background-size: 100px;
  background-position-y: -20px;
  background-image: url("@/assets/me.jpg");
  border-radius: 50%;
  overflow: hidden;
}

.about__wrapper {
  margin-left: 2rem;
  justify-content: flex-start;
  display: flex;
  flex-direction: column;
}

.about__since-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border-radius: 20px;
  width: 40%;
  background: -webkit-linear-gradient(45deg, rgb(34, 55, 114), rgb(76, 82, 112));
}


.about__tech-name {
  margin-bottom: 0;

}

.about__tech-time {
  margin-top: 0;
}

.about__name {
  font-weight: 700;
  text-align: left;
  margin: 0;
}

.about__time {
  font-weight: 700;
  text-align: left;
  margin: 0;
  color: #acaec9;
}

.about__position {
  text-align: left;
  margin: 0;
  color: #818cf8;;
}

.about__about-name {
  text-align: left;
}

.about__about-desc {
  text-align: left;

}

.about__grid {
  margin: 2rem auto 0 auto;
  width: 80%;
  display: flex;
  gap: 1.5rem;
  flex-wrap: wrap;
}

.about__grid-title {
  font-size: 1.1rem;
  font-weight: 700;
}

.about__div-wrapper {
  padding-top: 1rem;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1rem;
  flex-wrap: wrap;
}

.about__technology {
  margin-top: unset;
  width: 47%;
  margin-bottom: unset;
  box-sizing: border-box;
  background: -webkit-linear-gradient(45deg, rgb(34, 55, 114), rgb(76, 82, 112));
  padding: 12px;
  justify-content: center;
  align-items: center;
  display: flex;
  border-radius: 30px;
}


.about__card {
  display: flex;
  flex-wrap: wrap;
  flex-direction: column;
  text-align: left;
  animation: scale 2s;
  min-height: 20rem;
  flex: 1 0 min(300px, 100%);
  border-radius: 1.2rem;
  box-sizing: border-box;
  background: -webkit-linear-gradient(45deg, rgba(11, 21, 49, 0.62), rgba(39, 48, 87, 0.62));
  -webkit-box-shadow: 0px 0px 24px 0px rgba(14, 23, 49, 0.62);
  -moz-box-shadow: 0px 0px 24px 0px rgba(14, 23, 49, 0.62);
  box-shadow: 0px 0px 24px 0px rgba(14, 23, 49, 0.62);
  padding: 1rem;
}

@keyframes scale {
  0% {
    scale: 1.1;
  }
  100% {
    scale: 1;
  }
}

@media screen and (max-width: 900px) {
  .about__div-wrapper {
    flex-direction: column;
  }
  .about__since-wrapper{
    width: 80%;
  }
}

</style>
