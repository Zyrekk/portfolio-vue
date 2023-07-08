<template>
  <section class="welcome">
    <div class="welcome__left">
      <div class="welcome__left-wrapper">
        <h2 class="welcome__position-text">Fronted</h2>
        <span class="welcome__position-text-secondary">developer</span>
      </div>
      <h3 class="welcome__welcome-text">I'm pleased to welcome you to my frontend world, where you can get to know me
        and my skills better</h3>
    </div>
    <div class="welcome__carousel">
      <div class="welcome__carousel-first"/>
      <div class="welcome__carousel-second"/>
<!--      <div class="welcome__left-wrapper">-->
<!--        <h2 class="welcome__position-text">Fronted</h2>-->
<!--        <span class="welcome__position-text-secondary">developer</span>-->
<!--      </div>-->
<!--      <h3 class="welcome__welcome-text">I'm pleased to welcome you to my frontend world, where you can get to know me-->
<!--        and my skills better</h3>-->
    </div>
  </section>

</template>

<script>
export default {
  name: "WelcomeComponent",
  setup() {
  }
}
</script>

<style lang="scss" scoped>

.welcome {
  display: flex;
  flex-wrap: wrap;
  box-sizing: border-box;
  max-width: 90vw;
  width: 100%;
}

.welcome__left {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 0 10rem;
}

.welcome__left-wrapper{
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
  align-items: center;
}
.welcome__position-text {
  font-size: 4rem;
  background: -webkit-linear-gradient(19deg, #eee, #818cf8);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.welcome__position-text-secondary{
  all: unset;
  font-weight: 600;
  color: #818cf8;
  font-size: 4rem;
  padding-left: 1rem;
}

.welcome__welcome-text {
  box-sizing: border-box;
  max-width: 531.6px;
  text-align: left;
}

.welcome__carousel{
  animation: float 6s ease-in-out infinite;
  margin-left: 8rem;
  width: 25%;
  position: relative;
}

.welcome__carousel-first{
  width: 100%;
  aspect-ratio: 1/1;
  border-radius: 20px;
  //background-color: blue ;
  border: 2px solid blue;

}
.welcome__carousel-second{
  position: absolute;
  width: 100%;
  aspect-ratio: 1/1;
  border-radius: 20px;
  border: 2px solid #d1d1e0;
  //background-color: white;
  bottom: 0;
  right: 0;
  transform: translate(50%,50%);
}

@keyframes float {
  0% {
    box-shadow: 0 5px 15px 0px rgba(3,7,18,0.6);
    transform: translatey(0px);
  }
  50% {
    box-shadow: 0 25px 15px 0px rgba(3,7,18,0.2);
    transform: translatey(-15px);
  }
  100% {
    box-shadow: 0 5px 15px 0px rgba(3,7,18,0.6);
    transform: translatey(0px);
  }
}

@media screen and (max-width: 900px) {
  .welcome{
    justify-content: center;
    margin: 0 auto;
  }
  .welcome__left-wrapper{
    justify-content: center;
  }
  .welcome__left {
    padding: 0 0;
  }
  .welcome__position-text{
    margin-bottom: 0 ;
  }
  .welcome__position-text-secondary{
    margin-top: 0 ;
  }
  .welcome__carousel{
    margin-top: 3rem;
    margin-left: -6rem;
    width: 55%;
  }

}

</style>
