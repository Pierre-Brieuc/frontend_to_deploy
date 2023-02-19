<template>
    <div>
        <h1>Disconnect</h1>
        <button @click="disconnect">Disconnect</button>
    </div>
</template>

<script>
import Cookies from 'js-cookie'

export default {
  name: 'DisconnectView',
  computed: {
    disconnect () {
      Cookies.remove('token')
      Cookies.remove('count')
      location.reload()
      return 0
    }
  }
}
</script>
