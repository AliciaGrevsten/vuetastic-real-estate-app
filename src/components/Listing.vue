<!-- 
* Adress
* Real Estate Agent contact information
* Images (full gallery)
-->
<template>
  <div class="container">
     <div class="container">
    <div  v-bind:key="listing.id" v-for="listing in data">
         <div v-bind:key="agent.id" v-for="agent in data">
    
      <div class="card" v-bind:key="listing.address" v-for="listing in agent.listings">  
            <div class="img" v-bind:key="image.id" v-for="image in listing.images">
           <img v-bind:src="image" /> </div>
            <p>Adress: {{ listing.address }}</p>
            <p>Description: {{ listing.description }}</p>
            <p>Latitude: {{ listing.latitude }}</p>
            <p>Longitude: {{ listing.longitude }}</p>
            
          
            <br>
            <p>Agent: {{agent.first_name}} {{agent.last_name}}</p>
            <p>Telephone: {{agent.telephone}}</p>
            <p>Email: {{agent.email}}</p>
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
  width: 60%;
    margin: auto;
    color: rgb(77, 99, 119);
}
.card {
    width: 25%;
  color: white;
  min-height: 400px;
  background-color: rgb(133, 197, 199);
  padding: 2%;
  margin-left: 90%;
  margin-bottom: 2%;
  border-radius: 12px;
}
img{
      height: 50%;
  width: 100%;
  display: block;
  
}

</style>
