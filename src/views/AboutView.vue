<template>
  <AboutContainer/>
</template>

<script>
import AboutContainer from "@/components/About/AboutContainer.vue";

export default {
  name: "AboutView",
  components: {AboutContainer},
  setup(){
    window.scrollTo({
      top: 0,
      behavior: 'smooth'
    });
  }
}
</script>

<style scoped>

</style>
