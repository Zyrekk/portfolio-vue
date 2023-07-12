<template>
  <ContactContainer/>
</template>

<script>
import ContactContainer from "@/components/Contact/ContactContainer.vue";

export default {
  name: "ContactView",
  components:{ContactContainer},
  setup() {
    window.scrollTo({
      top: 0,
      behavior: 'smooth'
    });
  }
}
</script>

<style scoped>

</style>
