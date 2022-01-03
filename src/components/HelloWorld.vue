<template>
  <div>
    <h2>Filter LearnVue Articles</h2>
    <input type="text" placeholder="Filter Search" v-model="query" />
    <button @click="reset">Reset</button>
    <br />
    <SearchResults :query="query" />
  </div>
</template>

<script>
import { ref } from "vue";

import SearchResults from "./SearchResults.vue";

export default {
  name: "HelloWorld",
  components: {
    SearchResults,
  },
  setup() {
    const query = ref("");

    const reset = (event) => {
      query.value = "";
    };

    return {
      query,
      reset,
    };
  },
};
</script>

<style>
button {
  margin: 12px;
  font-size: 12px;
  font-family: "Courier New", Courier, monospace;
  font-weight: 100;
  height: 30px;
  width: 4%;
}
input:hover {
  background-color: #d3d3d3;
}
input {
  width: 20%;
  height: 30px;
}
</style>
