<template>
  <Header header-title="El Portafolio de Adrix" />
  <container />
  <Footer />
</template>

<script>
import Container from './components/Container.vue'
import Footer from './components/Footer.vue'
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    Container
  }
}
</script>

<style>

</style>
