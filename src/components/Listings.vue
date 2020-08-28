<!--
* Adress
* Real Estate Agent
* Image (1 or more)
* Link to navigate to single listing information component
-->
<template>
  <div class="container">
    <h1>Listings</h1>
    <div class="cardgroup" v-bind:key="agent.id" v-for="agent in data">
      <div class="card" v-bind:key="listing.adress" v-for="listing in agent.listings">
        <h3 class="card-header">Adress: {{ listing.address }}</h3>
        <div class="card-body">
          <h5 class="card-title">
            <a href="#" class="card-link" @click="$emit('show-agent', agent.id)">Agent: {{ agent.first_name }} {{ agent.last_name }}</a>
          </h5>
        </div>
        <img
          src="data:image/svg+xml;charset=UTF-8,%3Csvg%20width%3D%22318%22%20height%3D%22180%22%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20viewBox%3D%220%200%20318%20180%22%20preserveAspectRatio%3D%22none%22%3E%3Cdefs%3E%3Cstyle%20type%3D%22text%2Fcss%22%3E%23holder_158bd1d28ef%20text%20%7B%20fill%3Argba(255%2C255%2C255%2C.75)%3Bfont-weight%3Anormal%3Bfont-family%3AHelvetica%2C%20monospace%3Bfont-size%3A16pt%20%7D%20%3C%2Fstyle%3E%3C%2Fdefs%3E%3Cg%20id%3D%22holder_158bd1d28ef%22%3E%3Crect%20width%3D%22318%22%20height%3D%22180%22%20fill%3D%22%23777%22%3E%3C%2Frect%3E%3Cg%3E%3Ctext%20x%3D%22129.359375%22%20y%3D%2297.35%22%3EImage%3C%2Ftext%3E%3C%2Fg%3E%3C%2Fg%3E%3C%2Fsvg%3E"
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
  height: 200px;
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