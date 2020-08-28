<template>
  <div class="container">
    <h1>Listings</h1>
    <div class="cardgroup" v-bind:key="agent.id" v-for="agent in displayedListings">
      <div class="card" v-bind:key="listing.address" v-for="listing in agent.listings">
        <div class="card-body left">
          <img v-bind:src="listing.images[0]" alt="Picture of listing" />
        </div>
        <div class="card-body right">
          <h4 class="card-header">{{ listing.address }}</h4>
          <h5 class="card-title">
            Agent:
            <a
              href="#"
              v-bind:key="agent.id"
              v-on:click="$emit('show-agent', agent.id)"
              class="card-link"
            >{{ agent.first_name }} {{ agent.last_name }}</a>
          </h5>
          <br />
          <a
            href="#"
            v-bind:key="listing"
            v-on:click="$emit('show-listing', listing, agent.id)"
            class="card-link"
          >Read More..</a>
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
  },
};
</script>

<style scoped>
.card {
  width: 100%;
  color: white;
  min-height: 250px;
  align-items: stretch;
  box-sizing: border-box;
  padding: 1% 2%;
  margin: 1% 0% 3% 0%;
  border-bottom: 1px dotted rgba(77, 99, 119, 0.384);
  border-radius: 4px;
}
.title {
  padding: 1% 1% 4% 1%;
}
.left,
.right {
  padding: 4%;
  float: left;
}
.left {
  width: 40%;
}
.right {
  width: 40%;
}
h5,
h4 {
  color: rgb(77, 99, 119);
}
img {
  height: 100%;
  width: 90%;
  display: block;
}
a {
  text-decoration: none;
  color: rgb(58, 82, 104);
}
a:hover {
  color: rgb(31, 147, 255);
}
</style>