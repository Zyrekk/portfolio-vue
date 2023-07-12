<template>
  <section class="quick-about">
    <div class="quick-about__image"/>
    <div class="quick-about__event-wrapper">
      <h3 class="quick-about__text">More about me</h3>
      <span class="quick-about__text--secondary">Click the button below to read more.</span>
      <button class="quick-about__button" @click="handleAbout">About me</button>
    </div>
  </section>
</template>

<script>
import {useRouter} from "vue-router";

export default {
  name: "QuickAbout",
  setup(){
    const router = useRouter()
    const handleAbout = () => {
      router.push('/about')
    }
    return{handleAbout}
  }
}
</script>

<style lang="scss" scoped>

.quick-about {
  flex-wrap: wrap;
  margin: 7rem auto 0 auto;
  max-width: min(1440px, 90vw);
  width: 100%;
  display: flex;
  gap: 2rem;
  justify-content: center;
  align-items: center;
}

.quick-about__image{
  object-fit: contain;
  width: 150px;
  height: 150px;
  background-size: 150px;
  background-position-y:-30px ;
  background-image: url("@/assets/me.jpg");
  border-radius: 50%;
  overflow: hidden;
}

.quick-about__event-wrapper {
  display: flex;
  flex-direction: column;
}

.quick-about__text {
  margin-top: 0;
  text-align: left;
  margin-bottom: 0;
}

.quick-about__text--secondary {
  margin-top: 0;
  color: #acaec9;
  text-align: left;
}

.quick-about__button{
  all: unset;
  cursor: pointer;
  margin-top: 2rem;
  width: fit-content;
  padding: 15px 25px;
  border-radius: 30px;
  background: #818cf8;
  transition: .2s ease;
  &:hover{
    background: #525aab;
    transform: translateY(-5px);
  }
}

@media screen and (max-width: 490px) {
  .quick-about{
    flex-direction: column;
  }
  .quick-about__event-wrapper{
    align-items: center;
  }

}


</style>
