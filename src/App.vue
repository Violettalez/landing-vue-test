<script>
import Menu from './components/Menu.vue'
import Intro from './components/Intro.vue'
import GettingStarted from './components/GettingStarted.vue'
import FAQ from './components/FAQ.vue'
export default {
  components: {
    Menu,
    Intro,
    GettingStarted,
    FAQ,
  },
}
</script>

<template>
  <Menu />
  <Intro />
  <GettingStarted />
  <FAQ />
</template>

<style scoped></style>
