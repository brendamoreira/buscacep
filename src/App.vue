<template>
  <div id="app">
    <search class="search" @search="requestCep"/>
    <loading v-if="loading"/>
    <address-card :address="addressObject"/>
    <not-found v-if="notFound"/>
  </div>
</template>

<script>
import axios from 'axios'
import Search from './components/Search.vue'
import AddressCard from './components/AddressCard.vue'
import Loading from './components/Loading.vue'
import NotFound from './components/NotFound.vue'

export default {
  name: 'App',
  components: {
    Search, 
    AddressCard, 
    Loading, 
    NotFound
  },
  data() {
    return {
      addressObject: null,
      loading: false,
      notFound: false
    }
  },
  methods: {
    requestCep(cep){
      this.loading = true;
      this.notFound = false;
      axios
      .get(`https://viacep.com.br/ws/${cep}/json/`)
      .then(response => {
        this.addressObject = response.data
      })
      .catch(error => {
        this.notFound = true
      })
      .finally(() => {
        this.loading = false;
      })
    }
  }
}
</script>

<style>
#app {
  width: 100vw;
  height: 100vh;
  background-image: linear-gradient(to right top, #0087c2, #009cc9, #00afc1, #00c0ab, #37cd8d);
}
.search {
  margin: 50px;
}
</style>
