<template>
    <h1>More Information</h1>
    <div class="cardgroup" v-if="isSelected">
        <div class="card">
          <div class="card-body">
            <h4>Address: {{ listing.address }}</h4>
            <h4>Description: {{ listing.description }}</h4>
            <h4>Latitude: {{ listing.latitude }}</h4>
            <h4>Longitude: {{ listing.longitude }}</h4>

            <br />
            <h4>Agent: {{agent.first_name}} {{agent.last_name}}</h4>
            <h4>Phone: {{agent.telephone}}</h4>
            <h4>Email: {{agent.email}}</h4>

            <div class="img" v-bind:key="image.id" v-for="image in listing.images">
              <img v-bind:src="image" />
            </div> 
          </div>
        </div>
    </div>
</template>

<script>
export default {
  name: "Listing",
  props: ["listing", "agent", "isSelected"],
};
</script>

<style scoped>
.card {
  width: 100%;
  color: rgb(77, 99, 119);
  padding: 2% 4%;
  box-sizing: border-box;
  margin: 1%;
}
img{
  height: 50%;
  width: 100%;
  display: block;
}

</style>
