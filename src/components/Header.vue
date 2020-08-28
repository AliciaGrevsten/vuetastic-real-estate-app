<template>
  <div class="header">
    <div class="container">
      <img src="../assets/images/Vuetastic-Real-Estate-Icon.png" />
      <h1>VUEtastic Real Estate</h1>
      <nav>
        <div class="row">
 <div class="col one">
          <h2>Agent Profile</h2>
        </div>
        <div class="col two">
          <h2>Current Listings</h2>
        </div>
        <div class="col three">
          <h2>Listing Information</h2>
        </div>
        </div>
      </nav>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
  props: {
    msg: String,
  },
};
</script>

<style scoped>
.header {
  margin: 0%;
  border-bottom: 1px solid rgb(22, 52, 80);
  background-color: rgba(255, 255, 255, 0.541);
  background-image: url("https://i.redd.it/6eo12pidcly21.jpg");
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position-y: 64%;
  background-position-x: 50%;
  background-size: auto;
}
.container {
  background-color: rgba(250, 250, 250, 0.658);
  padding: 0%;
}
.row {
  background-color: transparent;
  padding: 0%;
  margin: 0%;
  color: black;
}
.one{
float: left;
  width: 22%;
} 
.three {
  float: left;
  width: 20%;
}
.two {
  width: 50%;
  float: left;
}
h1 {
  font-size: 50px;
  color: rgb(22, 52, 80);
  padding: 0%;
  margin: 0%;
}
h2:hover{
  text-shadow: 2px 2px rgb(92, 131, 103);
}
img {
  height: 100px;
}
</style>