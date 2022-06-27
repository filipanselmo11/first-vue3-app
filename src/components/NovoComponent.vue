<template>
  <div>
    <h2>Filter LearnVue Articles</h2>
    <input type="text" placeholder="Filter Search" v-model="query" />
    <br />
    <br />
    <button @click="reset">Reset</button>
    <search-results :query="query"></search-results>
  </div>
</template>

<script>
import { ref } from "vue";
import SearchResults from "./SearchResults.vue";
export default {
  components: { SearchResults },
  setup() {
    const query = ref("");
    const reset = (e) => {
      query.value = "";
    };
    return {
      query,
      reset,
    };
  },
};
</script>

<style scoped>
.root {
  width: 400px;
  margin: 0 auto;
}
.root p {
  text-align: right;
  font-size: 0.7em;
  margin: 0;
}
ul {
  list-style: none;
  width: 50px 0;
  padding: 0;
  background-color: #fafafa;
  border-radius: 5px;
  border: 1px solid #ddd;
}
li {
  text-align: left;
  padding: 20px;
  border-bottom: 1px solid #ddd;
}
li:nth-last-of-type(1) {
  border-bottom: none;
}
</style>
