<template>

  <div v-if="darkMode" class="Effect">
    <span class="Bar"></span>
    <span class="Light"></span>
    <span class="Light2"></span>
    <span class="Circle"></span>
  </div>
  <div v-else class="Effect">
    <span class="Bar light"></span>
    <span class="Light light"></span>
    <span class="Light2 light"></span>
    <span class="Circle light"></span>
  </div>
</template>

<script>
export default {
  name: "LightEffectComp",
  props: ['darkMode'],
}
</script>

<style scoped>
.Effect {
  margin-top: -20px;
  width: 100%;
  position: relative;
}

.Bar {
  position: absolute;
  left: 50%;
  transform: translate(-50%);
  bottom: -30px;
  width: 35%;
  height: 4px;
  /*background: linear-gradient(rgba(255,255,255,.3), rgba(255, 255, 255, .3));*/
  border-radius: 50%;

}

.Light {
  position: absolute;
  left: 50%;
  width: 50%;
  height: 20rem;
  background: rgba(85, 43, 215, 0.1);
  transform: translate(-50%) perspective(12em) rotateX(20deg);
  filter: blur(70px);
}

.Light.light{
  background: rgba(43, 215, 92, 0.1);
}

.Light2 {
  position: absolute;
  left: 50%;
  bottom: -550px;
  width: 18rem;
  height: 20rem;
  background: rgba(255, 255, 255, 0.3);
  transform: translate(-50%) perspective(5em) rotateX(160deg) scale(1, 0.6);
  box-shadow: 8px 8px 24px 0 rgba(255, 255, 255, 0.35);
  filter: blur(70px);
}

.Light2.light{
  background: rgba(201, 190, 190, 0.3);
  box-shadow: 8px 8px 24px 0 rgba(201, 190, 190, 0.35);

}

.Circle {
  position: absolute;
  left: 50%;
  min-width: 98vw;
  max-width: 99vw;
  height: 100rem;
  border-radius: 50%;
  background: rgba(85, 43, 215, 0.1);
  transform: translate(-50%);
  filter: blur(60px);
}

.Circle.light{
  background: rgba(43, 215, 92, 0.1);
}

</style>