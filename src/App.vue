<template>
  <div id="app">
    <link
      href="https://fonts.googleapis.com/css2?family=Quicksand:wght@300&display=swap"
      rel="stylesheet"
    />
    <link href="https://fonts.googleapis.com/css2?family=Sacramento&display=swap" rel="stylesheet" />

    <Header></Header>

    <div class="row">
      <div class="col profile">
        <AgentProfile v-bind:agent="agent" v-bind:isSelected="agentIsSelected"></AgentProfile>
      </div>
      <div class="col listings">
        <Listings v-bind:data="data" v-on:show-listing="showListing" v-on:show-agent="showAgent"></Listings>
      </div>
      <div class="col listing">
        <Listing 
          v-bind:listing="selectedListing"
          v-bind:agent="listingAgent"
          v-bind:isSelected="listingIsSelected"
        ></Listing>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import AgentProfile from "./components/AgentProfile.vue";
import Listing from "./components/Listing.vue";
import Listings from "./components/Listings.vue";
import json from "./assets/house_data.json";

export default {
  name: "App",
  components: {
    Header,
    AgentProfile,
    Listing,
    Listings,
  },
  data() {
    return {
      data: json,
      agentIsSelected: false,
      listingIsSelected: false,
      agent: {},
      selectedListing: {},
      listingAgent: {},
    };
  },
  methods: {
    showAgent(agentId) {
      this.data.forEach((agent) => {
        if (agent.id == agentId) {
          this.agent = agent;
          this.agentIsSelected = true;
        }
      });
    },
    showListing(listing, agentId) {
      this.data.forEach((agent) => {
        if (agent.id == agentId) {
          this.selectedListing = listing;
          this.listingAgent = agent;
          this.listingIsSelected = true;
        }
      });
    },
  },
};
</script>

<style>
#app {
  font-family: "Quicksand", sans-serif;
  text-align: center;
  color: rgb(22, 52, 80);
  margin: 0%;
  padding: 0%;
  background-color: rgb(255, 255, 255);
  background-image: url("https://vistapointe.net/images/white-10.jpg");
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: center;
  background-size: auto; 
}

.profile {
  width: 22%;
  margin: 1% 1%;
  float:left;
  color: rgb(22, 52, 80);
}
.listings {
  width: 46%;
  float: left; 
  color: rgb(22, 52, 80);
  padding: 1%;
}
.listing {
  float: left;
  width: 22%;
  color: rgb(22, 52, 80);
  margin: 1% 1%;
  text-align: left;
}
.row:after {
  content: "";
  display: table;
  clear: both;
}
h1,
h3 {
  font-family: "Quicksand", sans-serif;
}

</style>
