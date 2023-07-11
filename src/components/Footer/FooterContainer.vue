<template>
  <div class="footer">
    <h3 class="footer__dev">zyrekk.dev</h3>
    <div class="footer__wrapper">
      <button class="footer__button">About</button>
      <a class="footer__github-link" href="https://github.com/Zyrekk" rel="noreferrer" target="_blank">
        <button class="footer__button">GitHub</button>
      </a>
      <button class="footer__button">Contact</button>
    </div>
    <div class="footer__wave footer__wave--1"/>
    <div class="footer__wave-2 footer__wave--2"/>
  </div>
</template>

<script>
export default {
  name: "FooterContainer"
}
</script>

<style lang="scss" scoped>

.footer {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 100%;
  position: relative;
  margin-top: 12rem;
}

.footer__dev {
  font-size: 2rem;
}

.footer__github-link {
  all: unset;
}


.footer__wrapper {
  z-index: 100;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  gap: 2rem;
  margin-bottom: 4rem;
}

.footer__button {
  all: unset;
  cursor: pointer;
  padding: 15px 25px;
  border-radius: 10px;
  background: #818cf8;
  transition: .2s ease;
  font-weight: 700;

  &:hover {
    background: #525aab;
  }
}

.footer__wave, .footer__wave-2 {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-image: url("@/assets/Wave2.svg");
  opacity: 0.1;
}

.footer__wave-2 {
  animation: scale 2s;
  height: 60%;
}

.footer__wave--1 {
  animation: animate 40s linear infinite;
}

.footer__wave--2 {
  animation: animate2 45s linear infinite;
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
    background-position-x: 0px;
  }
  100% {
    background-position-x: 1440px;
  }
}

@media screen and (max-width: 768px) {
  .footer {
    margin-top: 4rem;
  }
}


</style>
