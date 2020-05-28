<template>
  <div id="app">
    <search class="search" @search="requestCep"/>
    <loading v-if="loading"/>
    <address-card :address="addressObject"/>
  </div>
</template>

<script>
import axios from 'axios'
import Search from './components/Search.vue'
import AddressCard from './components/AddressCard.vue'
import Loading from './components/Loading.vue'

export default {
  name: 'App',
  components: {
    Search, AddressCard, Loading
  },
  data() {
    return {
      addressObject: null,
      loading: false
    }
  },
  methods: {
    requestCep(cep){
      this.loading = true;
      axios
      .get(`https://viacep.com.br/ws/${cep}/json/`)
      .then(response => {
        this.addressObject = response.data;
        this.loading = false;
      })
    }
  }
}
</script>

<style>
.search {
  margin: 50px;
}
</style>
