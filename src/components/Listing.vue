<!-- 
* Adress
* Real Estate Agent contact information
* Images (full gallery)
-->
<template>
  <div class="container">
    <h1>Listing</h1>
    <div class="cardgroup" v-bind:key="listing.id" v-for="listing in data">
      <div v-bind:key="agent.id" v-for="agent in data">
        <div class="card" v-bind:key="listing.id" v-for="listing in listing.listings">
          <div class="card-body">
            <div class="img" v-bind:key="image.id" v-for="image in listing.images">
              <img v-bind:src="image" />
            </div>
            <p>Adress: {{ listing.address }}</p>
            <p>Description: {{ listing.description }}</p>
            <p>Latitude: {{ listing.latitude }}</p>
            <p>Longitude: {{ listing.longitude }}</p>

            <br />
            <p>Agent: {{agent.first_name}} {{agent.last_name}}</p>
            <p>Telephone: {{agent.telephone}}</p>
            <p>Email: {{agent.email}}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Listing",
  props: ["data"],
};
</script>

<style scoped>
.container {
  color: rgb(133, 197, 199);
}
.card {
  width: 20%;
  color: white;
  background-color: rgb(133, 197, 199);
  padding: 1%;
  margin: 1%;
  float: left;
  border-radius: 12px;
}
img {
  display: block;
  width: 100%;
}
</style>
