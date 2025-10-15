<script>
import Menu from './components/Menu.vue'
import Intro from './components/Intro.vue'
import GettingStarted from './components/GettingStarted.vue'
import FAQ from './components/FAQ.vue'
import ContactUs from './components/ContactUs.vue'
export default {
  components: {
    Menu,
    Intro,
    GettingStarted,
    FAQ,
    ContactUs,
  },
}
</script>

<template>
  <Menu />
  <Intro />
  <GettingStarted />
  <FAQ />
  <ContactUs />
</template>

<style scoped></style>
