<template>
  <nav class="navbar navbar-expand-lg navbar-custom navbar-light">
    <div class="container">
      <router-link class="navbar-brand text-covid" to="/">COVID-19 Tracker</router-link>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarResponsive"
        aria-controls="navbarResponsive" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarResponsive">
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <router-link class="nav-link" to="/">Home</router-link>
          </li>
          <li class="nav-item" v-if="getRoute === '/'">
            <a class="nav-link" href="#tips" v-smooth-scroll>Tips</a>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/tracking">Tracking</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
// import router from '@/router'

export default {
  name: 'Navbar',
  computed: {
    getRoute () {
      return this.$route.path
    }
  }
}
</script>

<style scoped>
.navbar-custom .navbar-nav .nav-item .nav-link.exact-active {
  color: #b71c1c !important;
  font-weight: 800;
}
</style>
