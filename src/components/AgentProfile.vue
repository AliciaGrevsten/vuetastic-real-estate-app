
<template>
  <div class="container">
    <h1>Agent Profile</h1>
    <div class="cardgroup" v-if="isSelected">
      <div class="card">
        <h3>{{agent.first_name}} {{agent.last_name}}</h3>
        
        <img :src="require( `@/assets/images/${agent.profile_image}`)" alt="Profile image"/>
       
        <h4>Phone: {{agent.telephone}}</h4>
        <h4>Mail: {{agent.email}}</h4>

        <h4>Listings: </h4>
        <ul v-bind:key="listing.adress" v-for="listing in agent.listings">
          <li>{{listing.address}}</li>
        </ul>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "AgentProfile",
 props: ["agent", "isSelected"]
};
</script>

<style scoped>
.card {
  width: 100%;
  color: rgb(77, 99, 119);
  padding: 2%;
  margin: 1% 0%;
  box-sizing: border-box;
}
h3 {
  font-family: 'Quicksand', sans-serif; 
}
h4, p {
  text-align: left;
  color: rgb(58, 82, 104);;
}
img {
  height: 200px;
  width: 80%;
  display: block;
  border-radius: 200px;
  margin: auto;
}
</style>