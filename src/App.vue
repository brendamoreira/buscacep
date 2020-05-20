<template>
  <div id="app">
    <search/>
    <loading/>
    <address-card/>
  </div>
</template>

<script>
import Search from './components/Search.vue'
import AddressCard from './components/AddressCard.vue'
import Loading from './components/Loading.vue'

export default {
  name: 'App',
  components: {
    Search, AddressCard, Loading
  }
}
</script>

<style>

</style>
