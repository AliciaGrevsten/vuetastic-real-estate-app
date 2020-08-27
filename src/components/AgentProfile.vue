<!--
* Agent information
    * Name
    * Phonenumber
    * Email
    * Profile Image
    * List of listings
-->

<template>
  <div>
    <div v-bind:key="agent.id" v-for="agent in agents"></div>
    <h3>{{agent.first_name}} {{agent.last_name}}</h3>
    <h4>{{agent.telephone}}</h4>
    <h4>{{agent.email}}</h4>
    <img src alt />
    <!--{{agent.profile_image}}-->
    <ul>{{agent.listings}}</ul>
  </div>
</template>


<script>
export default {
  name: "",
  props: ["agents"],
};
</script>

<style scoped>
</style>