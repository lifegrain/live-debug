<template>
  <div id="app">
    <vue-progress-bar></vue-progress-bar>
    <Navbar/>
    <router-view/>
    <Footer/>
  </div>
</template>

<script>
import Navbar from './components/Navbar'
import Footer from './components/Footer'
import router from '@/router'

export default {
  name: 'App',
  components: {
    Navbar,
    Footer
  },
  mounted () {
    this.$Progress.finish()
  },
  created () {
    this.$Progress.start()
    router.beforeEach((to, from, next) => {
      if (to.meta.progress !== undefined) {
        const meta = to.meta.progress
        this.$Progress.parseMeta(meta)
      }
      this.$Progress.start()
      next()
    })
    router.afterEach((to, from) => {
      this.$Progress.finish()
    })
  }
}
</script>

<style>

</style>
