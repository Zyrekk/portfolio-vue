<template>
    <div class="footer__relative">
      <h3 class="footer__dev">zyrekk.dev</h3>
      <div class="footer__wrapper">
        <button class="footer__button" @click="handleAbout">About</button>
        <a class="footer__github-link" href="https://github.com/Zyrekk" rel="noreferrer" target="_blank">
          <button class="footer__button">GitHub</button>
        </a>
        <button class="footer__button" @click="handleContact">Contact</button>
      </div>
    </div>
</template>

<script>
import {useRouter} from "vue-router";

export default {
  name: "FooterContainer",
  setup(){
    const router=useRouter()

    const handleAbout=()=>{
      router.push('/about')
    }
    const handleContact=()=>{
      router.push('/contact')
    }

    return{handleAbout,handleContact}
  }
}
</script>

<style lang="scss" scoped>

.footer__relative {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  background: #181d44;
  width: 100%;
  position: relative;
  overflow: hidden;
  &:before,
  &:after {
    content: "";
    position: absolute;
    left: 50%;
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
@keyframes rotate {
  0% {transform: translate(-50%, 0) rotateZ(0deg);}
  50% {transform: translate(-50%, 2%) rotateZ(180deg);}
  100% {transform: translate(-50%, 0) rotateZ(360deg);}
}

.footer__dev {
  animation: scale 2s;
  font-size: 2rem;
  z-index: 20;
}

.footer__github-link {
  all: unset;
}


.footer__wrapper {
  margin: 0 2rem  4rem 2rem;
  z-index: 100;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  gap: 2rem;
}

.footer__button {
  all: unset;
  animation: scale 2s;
  padding: 15px 25px;
  border-radius: 10px;
  background: #818cf8;
  transition: .2s ease;
  font-weight: 700;
  cursor: pointer;
  &:hover {
    background: #525aab;
    transform: translateY(-5px);
  }
}

@keyframes scale {
  0%{
    scale: 1.2;
  }
  100%{
    scale: 1;
  }
}

@media screen and (max-width: 768px) {
  .footer {
    margin-top: 4rem;
  }
}


</style>
