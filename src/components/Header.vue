<template>
  <div class="header">
    <div class="container">
      <img src="../assets/images/Vuetastic-Real-Estate-Icon.png" />
      <h1>VUEtastic Real Estate</h1>
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
  background-position-y: 70%;
  background-position-x: 50%;
  background-size: auto;
}
.container {
  background-color: rgba(250, 250, 250, 0.658);
  padding: 1%;
}
h1 {
  font-size: 50px;
  color: rgb(22, 52, 80);
  padding: 0%;
  margin: 0%;
}
img {
  height: 100px;
}
</style>