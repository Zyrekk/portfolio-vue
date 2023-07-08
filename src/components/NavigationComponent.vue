<template>
  <div class="nav-container">
    <a class="nav-container__dev-name" href="">KRJ.dev</a>
    <nav class="nav-container__content">
      <button class="nav-container__button">
        <div class="nav-container__line"/>
        <div class="nav-container__line"/>
        <div class="nav-container__line"/>
      </button>
      <ul class="nav-container__links">
        <li class="nav-container__single-link">About</li>
        <li class="nav-container__single-link">GitHub</li>
        <li class="nav-container__single-link">Contact</li>
      </ul>
    </nav>
  </div>

</template>

<script>
export default {
  name: "NavigationComponent"
}
</script>

<style lang="scss" scoped>

.nav-container {
  display: flex;
  justify-content: center;
  width: 100%;
  margin-top: 3rem;
}

.nav-container__dev-name {
  text-decoration: none;
  color: white;
  display: flex;
  align-items: center;
  margin-left: 7rem;
  font-weight: 600;
  font-size: 1.875rem;
  line-height: 2.25rem;
  transition: 0.2s ease-in-out;
  cursor: pointer;

  &:hover {
    color: #4f46e5;

  }
}

.nav-container__content {
  position: relative;
  width: 100%;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: end;
  flex-grow: 1;
}

.nav-container__button {
  visibility: hidden;
  margin-right: 3.5rem;
  width: 2.2rem;
  gap: 8px;
  display: flex;
  flex-direction: column;
  transition: 0.2s ease-in-out;
}

.nav-container__line {
  transition: 0.2s ease-in-out;
  width: 100%;
  height: 2px;
  background: white;
}

.nav-container__links {
  list-style-type: none;
  display: flex;
  gap: 2.5rem;
  margin-right: 3.5rem;
}

.nav-container__single-link {
  font-size: 1.25rem;
  line-height: 1.75rem;
  font-weight: 600;
  cursor: pointer;
  color: white;
  transition: .2s ease-in-out;
  &:hover {
    color: #4f46e5;
  }

}

@media screen and (max-width: 768px) {
  .nav-container__button {
    visibility: visible;
  }
  .nav-container__links {
    position: absolute;
    align-items: start;
    flex-direction: column;
    right: 0;
    top: 4rem;
  }

}
</style>
