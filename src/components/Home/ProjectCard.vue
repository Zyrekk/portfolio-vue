<template>
  <div class="card">
    <div>
      <h3 class="card__title">{{ project.title }}</h3>
      <p class="card__title-desc">{{ project.desc }}</p>
      <div class="card__technology-wrapper">
        <div class="card__technology" v-for="item in project.tech" :key="item">
          {{ item }}
        </div>
      </div>
    </div>
    <a class="card__github-link" :href="project.link" rel="noreferrer" target="_blank">
      GitHub
    </a>
  </div>
</template>

<script>
import {ref} from "vue";

export default {
  name: "ProjectCard",
  props: ['info'],
  setup(props) {
    const project=ref(props.info)
    return{project}
  }

}
</script>

<style lang="scss" scoped>

.card{
  animation: scale 2s;
  display: flex;
  flex-direction: column;
  box-sizing: border-box;
  margin: 0 3rem;
  padding: 2rem;
  border-radius: 2rem;
  justify-content: space-between;
  flex: 1 0 min(300px,100%);
  align-items: center;
  -webkit-box-shadow: 0px 0px 24px 0px rgba(14, 23, 49, 0.62);
  -moz-box-shadow: 0px 0px 24px 0px rgba(14, 23, 49, 0.62);
  box-shadow: 0px 0px 24px 0px rgba(14, 23, 49, 0.62);
  background: -webkit-linear-gradient(45deg, rgba(11, 21, 49, 0.62), rgba(39, 48, 87, 0.62));
  backdrop-filter: blur(20px);
  transition: .3s ease;
  &:hover{
    transform: scale(0.98);
    -webkit-box-shadow: 0px 0px 24px 0px rgba(186, 192, 208, 0.4);
    -moz-box-shadow: 0px 0px 24px 0px rgba(186, 192, 208, 0.4);
    box-shadow: 0px 0px 24px 0px rgba(186, 192, 208, 0.4);
    //transform: scale(0.95);
  }
}

.card__title{
  width: 100%;
  margin-top: 1rem;
  text-align: left;
  font-weight: 700;
  font-size: 1.5rem;
}

.card__title-desc{
  width: 100%;
  text-align: left;
  color: #acaec9;
}

.card__technology{
  background: -webkit-linear-gradient(45deg, rgba(20, 38, 89, 0.62), rgba(63, 77, 138, 0.62));
  padding: 12px;
  display: flex;
  align-items: center;
  border-radius: 30px;
}

.card__technology-wrapper{
  width: 100%;
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.card__github-link{
  all: unset;
  cursor: pointer;
  margin-top: 4rem;
  width: fit-content;
  padding: 15px 25px;
  border-radius: 30px;
  background: #818cf8;
  transition: .2s ease;
  &:hover{
    background: #525aab;
  }
}

@keyframes scale {
  0% {
    scale: 1.1;
  }
  100% {
    scale: 1;
  }
}

</style>
