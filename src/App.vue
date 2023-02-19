<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link  v-if="isTokenEmpty()" to="/locations">Locations | </router-link>
    <router-link v-if="!isTokenEmpty()" to="/login">Login</router-link>
    <router-link v-if="isTokenEmpty()" to="/disconnect">Disconnect</router-link>
  </nav>
  <router-view/>
</template>

<script>
import Cookies from 'js-cookie'

export default {
  data () {
    return {
      token: Cookies.get('token')
    }
  },
  methods: {
    isTokenEmpty () {
      if (Cookies.get('token') === null) {
        return false
      } else {
        return true
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
  position: fixed;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
