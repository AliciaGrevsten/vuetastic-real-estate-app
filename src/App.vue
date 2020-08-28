<template>
  <div id="app">
    <Header msg="Vuetastic Real Estate"></Header>

    <div class="col profile">
      <AgentProfile v-bind:data="data" v-bind:isClicked="isSelected"></AgentProfile>
    </div>
     <div class="col listings">
      <Listings v-bind:data="data" v-bind:isSelected="isSelected" v-on:show-agent="showAgent"></Listings>
    </div> 
    <div class="col listing">
      <Listing></Listing>
    </div> -->
  </div>
</template>

<script>
import Header from './components/Header.vue'
import AgentProfile from './components/AgentProfile.vue'
//import Listing from './components/Listing.vue'
import Listings from './components/Listings.vue'
import json from './assets/house_data.json'


export default {
  name: 'App',
  components: {
    Header, 
   AgentProfile,
    //Listing,
    Listings
  },
  data() {
    return {
      data: json,
      isSelected: false,
    }
  },
  methods:{
    showAgent(){
      this.isSelected = !this.isSelected;
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
</style>
