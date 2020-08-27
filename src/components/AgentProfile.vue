<!--
* Agent information
    * Name
    * Phonenumber
    * Email
    * Profile Image
    * List of listings
-->

<template>
  <div class="container">
<div class="cardgroup" v-bind:key="agent.id" v-for="agent in data">
    <h3>{{agent.first_name}} {{agent.last_name}}</h3>
    <h4>{{agent.telephone}}</h4>
    <h4>{{agent.email}}</h4>

     <img src="`${{agent.profile_image}}`" alt="Profile image" /> 
   
    <ul v-bind:key="listing.adress" v-for="listing in agent.listings">
      <li>{{listing.address}}</li>
       <li>{{listing.description}}</li>
        <li>{{listing.latitude}}</li>
         <li>{{listing.longitude}}</li>
          <img src="`${{listing.images}}`">
      
      </ul> 

</div>
  </div>
</template>


<script>
export default {
   name: "Agent",
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