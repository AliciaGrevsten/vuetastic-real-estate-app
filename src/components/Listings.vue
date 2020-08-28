<!--
* Adress
* Real Estate Agent
* Image (1 or more)
* Link to navigate to single listing information component
-->
<template>
  <div class="container">
    <h1 class="title">Listings</h1>
    <div class="cardgroup" v-bind:key="agent.id" v-for="agent in data">
      <div class="card" v-bind:key="listing.adress" v-for="listing in agent.listings">
        <h3 class="card-header">Adress: {{ listing.address }}</h3>
        <div class="card-body">
          <h5 class="card-title">
            <a href="#" class="card-link" @click="$emit('show-agent', agent.id)">Agent: {{ agent.first_name }} {{ agent.last_name }}</a>
          </h5>
        </div>
        <br>
        <img
        v-bind:src="listing.images[0]"
          alt="Picture of listing"
        />
        <br />
        <div class="card-body">
          <a href="#" class="card-link">Read More..</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Listings",
  props: ["data"],
};
</script>

<style scoped>
.container {
    width: 60%;
    margin: auto;
    color: rgb(77, 99, 119);
}
.card {
  width: 25%;
  color: white;
  min-height: 400px;
  align-items: stretch;
  background-color: rgb(133, 197, 199);
  padding: 1% 2%;
  margin: 2%;
  float: left;
  border-radius: 12px;
}
.title {
    padding: 1% 1% 4% 1%;
}
h3 {
    color: rgb(58, 82, 104);
}
img {
  height: 50%;
  width: 100%;
  display: block;
}
a {
  text-decoration: none;
  color: white;
}
a:hover {
  color: rgb(58, 82, 104);
}
</style>