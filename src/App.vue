<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <router-view/>
  {{ name }} / {{ typeof name }} <br>
  {{ num }} / {{ typeof num }} <br>
  {{ withquote }} / {{ typeof withquote }}
</template>

<style lang="scss">
@import 'bootstrap';
</style>

<script>
export default {
  data () {
    return {
      name: process.env.VUE_APP_ADMINNAME,
      num: process.env.VUE_APP_THISISNUMBER,
      withquote: process.env.VUE_APP_WITHQUOTE
    }
  }
}
</script>
