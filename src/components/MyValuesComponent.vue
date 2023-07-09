<template>
  <section class="values">
    <div class="values__item">
      <h3 class="values__number">1</h3>
      <div class="values__text-wrapper">
        <span class="values__text-title">Creativity</span>
        <span class="values__text-description">Innovative frontend solutions</span>
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
    <div class="values__wave values__wave--1"/>
  </section>

</template>

<script>
export default {
  name: "MyValuesComponent"
}
</script>

<style lang="scss" scoped>

.values {
  background: -webkit-linear-gradient(20deg, #525996, rgb(41, 46, 87));
  display: flex;
  position: relative;
  justify-content: space-evenly;
  width: 100%;
  height: 150px;
  margin: 18rem auto 0;
}

.values__item{
  display: flex;
  justify-content: center;
  gap: 1rem;
  align-items: center;
}

.values__number{
  color: #acaec9;
  font-size: 3rem;
  z-index: 12;
}

.values__text-wrapper{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;

}

.values__text-title{
  font-size: 1.3rem;
  z-index: 5;
}

.values__text-description{
  color: #acaec9;
  font-size: 1rem;
  text-align: start;
  z-index: 5;
}

.values__wave {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 110%;
  height: 60%;
  background-image: url("@/assets/Wave2.svg");
  opacity: 0.4;
}

.values__wave--1 {
  animation: animate 35s linear infinite;
}

@keyframes animate {
  0% {
    background-position-x: 0px;
  }
  100% {
    background-position-x: 1440px;
  }
}

@media screen and (max-width: 900px) {
  .values {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 10rem;
  }
}

</style>
