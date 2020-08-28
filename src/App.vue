<template>
  <div id="app">
    <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@300&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Sacramento&display=swap" rel="stylesheet">

    <Header></Header>

    <div class="col profile">
      <AgentProfile v-bind:data="data"></AgentProfile>
    </div>
     <div class="col listings">
      <Listings v-bind:data="data"></Listings>
    </div> 
     <!-- <div class="col listing">
       <Listing v-bind:data="data"></Listing>
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
    }
  }
}
</script>

<style>
#app {
  font-family: 'Quicksand', sans-serif;  
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rgb(58, 82, 104);
}

h1, h3 {
  font-family: 'Sacramento', cursive;
    color: rgb(58, 82, 104);

}
</style>
