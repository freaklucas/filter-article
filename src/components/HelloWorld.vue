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
input[type="text"] {
  margin-bottom: 20px;
  padding: 10px;
}
button {
  margin: 10px;
  width: 4%;
  height: 28px;
}
</style>

