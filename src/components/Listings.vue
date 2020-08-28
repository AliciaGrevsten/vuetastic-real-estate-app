<template>

  <div class="container">
    <h1 class="title">Listings</h1>
    <div class="cardgroup" v-bind:key="agent.id" v-for="agent in displayedListings">
      <div class="card" v-bind:key="listing.address" v-for="listing in agent.listings">
        <h4 class="card-header">{{ listing.address }}</h4>
        <div class="card-body">
          <h5 class="card-title">
            Agent:
            <a href="#" class="card-link">{{ agent.first_name }} {{ agent.last_name }}</a>
          </h5>
        </div>
        <br />
        <img v-bind:src="listing.images[0]" alt="Picture of listing" />
        <br />
        <div class="card-body">
          <a href="#" class="card-link">Read More..</a>
        </div>
      </div>
    </div>
  </div>

  <Observer v-on:intersect="intersected" />
</template>

<script>
import Observer from "./Observer.vue";

export default {
  name: "Listings",
  props: ["data"],
  components: {
    Observer,
  },
  data() {
    return {
      loadMore: true,
      currentPage: 1,
      pageSize: 2,
      index: 0,
      displayedListings: [],
    };
  },
  methods: {
    getDisplayListings() {
      // Fetches 2 agents listings in the array at a time
      this.data.forEach((agent) => {
        if (agent.id >= this.index && agent.id < this.index + this.pageSize) {
          this.displayedListings.push(agent);
        }
      });

      this.index += this.pageSize;
    },
    // Listens for scrolling
    async intersected() {
      await this.getDisplayListings();
      this.currentPage++;
    },
  }
};
</script>

<style scoped>
.container {
  width: 50%;
  margin: auto;
  color: rgb(77, 99, 119);
}
.card {
  width: 25%;
  color: white;
  min-height: 350px;
  align-items: stretch;
  background-color: rgb(133, 197, 199);
  padding: 1% 2%;
  margin: 2%;
  float: left;
  border-radius: 12px;
}
.title {
  padding: 1% 1% 4% 1%;
}
h4 {
  color: rgb(77, 99, 119);
}
img {
  height: 50%;
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