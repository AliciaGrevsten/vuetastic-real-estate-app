
<template>
  <div class="container">
    <div class="cardgroup">
      <div class="card">
        <h3>{{agent.first_name}} {{agent.last_name}}</h3>

        <img v-bind:src="agent.profile_image"  alt="Profile image" />
        
        <h4>Phone: {{agent.telephone}}</h4>
        <h4>Email: {{agent.email}}</h4>

        <p>Listings: </p>
        <ul v-bind:key="listing.adress" v-for="listing in agent.listings">
          <li>{{listing.address}}</li>
          <!-- <li>{{listing.description}}</li>
          <li>{{listing.latitude}}</li>
          <li>{{listing.longitude}}</li> -->
          <!-- <img v-bind:src="listing.images">  Tycker inte vi behöver detta-->
        </ul>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "AgentProfile",
 props: ["agent"]
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
h3 {
  font-family: 'Quicksand', sans-serif; 
}
h4, p {
  text-align: left;
}
img {
  height: 200px;
  width: 80%;
  display: block;
  border-radius: 200px;
  margin: auto;
}
</style>