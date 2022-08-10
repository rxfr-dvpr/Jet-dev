<template>
  <Nav/>
  <Header/>
  <Main/>
  <Footer/>
</template>

<script>
import FooterVue from './components/Footer.vue'
import HeaderVue from './components/Header.vue'
import MainVue from './components/Main.vue'
import NavVue from './components/Nav.vue'

export default {
  name: 'App',
  components: {
    Nav: NavVue,
    Header: HeaderVue,
    Main: MainVue,
    Footer: FooterVue
  }
}
</script>

<style lang="scss" scoped>


</style>
