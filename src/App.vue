<template>
<div id="main-div" class="d-flex flex-column justify-content-between">
  <Header header-title="Los repos de Dr. Madrix" />
  <container />
  <Footer />
</div>
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
#main-div{
  height: 100vh;
}
</style>
