<template>
  <div id="app">
    <Header msg="Vuetastic Real Estate"></Header>

    <div class="col profile">
      <AgentProfile></AgentProfile>
    </div>
    <div class="col listings">
      <Listings></Listings>
    </div>
    <div class="col listing">
      <Listing></Listing>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import AgentProfile from './components/AgentProfile.vue'
import Listing from './components/Listing.vue'
import Listings from './components/Listings.vue'


export default {
  name: 'App',
  components: {
    Header, 
    AgentProfile,
    Listing,
    Listings
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
  margin-top: 60px;
}
</style>
