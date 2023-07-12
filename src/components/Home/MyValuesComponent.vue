<template>
  <section class="values">
    <div class="values__wrapper">
      <div class="values__item">
        <h3 class="values__number">1</h3>
        <div class="values__text-wrapper">
          <span class="values__text-title">Creativity</span>
          <span class="values__text-description">Innovative solutions</span>
        </div>
      </div>
      <div class="values__item">
        <h3 class="values__number">2</h3>
        <div class="values__text-wrapper">
          <span class="values__text-title">Flexibility</span>
          <span class="values__text-description">Adaptable approach</span>
        </div>
      </div>
      <div class="values__item">
        <h3 class="values__number">3</h3>
        <div class="values__text-wrapper">
          <span class="values__text-title">Passion</span>
          <span class="values__text-description">Pixel-perfect creation</span>
        </div>
      </div>
    </div>
  </section>

</template>

<script>
export default {
  name: "MyValuesComponent"
}
</script>

<style lang="scss" scoped>

.values {
  animation: scale 2s;
  display: flex;
  justify-content: center;
  position: relative;
  background: -webkit-linear-gradient(90deg, #030712, #1b213e);
  width: 100%;
  margin: 18rem auto 0;
  overflow: hidden;
  &:before,
  &:after {
    content: "";
    position: absolute;
    left: 40%;
    min-width: 300vw;
    min-height: 300vw;
    background: #030712;
    animation: rotate infinite linear;
  }

  &:before {
    bottom: 7vh;
    border-radius: 45%;
    animation-duration: 10s;
  }

  &:after {
    bottom: 5vh;
    opacity: .5;
    border-radius: 47%;
    animation-duration: 10s;
  }
}

.values__wrapper{
  max-width: min(1440px,90vw);
  display: flex;
  width: 100%;
  justify-content: space-evenly;
  flex-wrap: wrap;
}

.values__item {
  display: flex;
  justify-content: center;
  gap: 1rem;
  align-items: center;
}

.values__number {
  animation: scale 2s;
  color: #acaec9;
  font-size: 3rem;
  z-index: 12;
  font-weight: 600;
}

.values__text-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;

}

.values__text-title {
  animation: scale 2s;
  font-size: 1.3rem;
  font-weight: 500;
  z-index: 5;
}

.values__text-description {
  animation: scale 2s;
  color: #acaec9;
  font-size: 1rem;
  font-weight: 600;
  text-align: start;
  z-index: 5;
}

.values__blur-bottom,.values__blur-top{
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 100%;
  filter: blur(1px);
  background: -webkit-linear-gradient(90deg, #030712, #1b213e);
  opacity: 1;
  height: 10px;
}

.values__blur-top{
  bottom: unset;
  top: -5px;
  background: -webkit-linear-gradient(90deg, #1b213e,#030712);
}

.values__wave,.values__wave-2 {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 50%;
  background-image: url("@/assets/Wave2.svg");
  opacity: 0.1;
}

.values__wave-2 {
  animation: scale 2s;
  height: 30%;
}

.values__wave--1 {
  animation: animate 35s linear infinite;
}

.values__wave--2 {
  animation: animate2 30s linear infinite;
}

@keyframes rotate {
  0% {transform: translate(-50%, 0) rotate(0deg);}
  50% {transform: translate(-50%, 2%) rotate(180deg);}
  100% {transform: translate(-50%, 0) rotate(360deg);}
}

@keyframes animate {
  0% {
    background-position-x: 0px;
  }
  100% {
    background-position-x: 1440px;
  }
}
@keyframes animate2 {
  0% {
    background-position-x: 1440px;
  }
  100% {
    background-position-x: 0px;
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

@media screen and (max-width: 1340px) {
  .values{
    margin: 24rem auto 0;
  }

}

@media screen and (max-width: 900px) {
  .values {
    padding: 2rem 0;
  }

  .values__item {
    width: 15rem;
    gap: 0.5rem;
    padding: 1rem 0;
  }
  .values__wave {
    width: 100%;
    background-size: cover;
  }

  .values__number {
    margin: 0;
    font-size: 2.5rem;
  }

  .values__text-title {
    font-size: 1.1rem;
  }

  .values__text-description {
    font-size: 0.8rem;
  }
}

@media screen and (max-width: 850px) {
  .values{
    margin: 18rem auto 0;
  }
}

@media screen and (max-width: 525px) {
  .values{
    margin: 14rem auto 0;
  }
}

@media screen and (max-width: 495px) {
  .values__item {
    justify-content: flex-start;
    padding-left: 28%;
  }

  .values__number {
    margin: 0;
  }

  .values__text-title {
    font-size: 1.1rem;
  }

  .values__text-description {
  }
}

</style>
