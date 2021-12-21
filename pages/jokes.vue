<template>
<div >
<SearchText v-on:search-text="searchText" />
    <h1 class="d-flex text-center">API Results</h1>
    <joke v-for="joke in jokes" :key="joke.id"
    :id="joke.id" :joke="joke.joke" />
</div>
</template>

<script>
import axios from "axios";
import joke from '../components/joke.vue';
import SearchText from '../components/searchText.vue';
export default {
  components: { joke, SearchText },
  name: "jokes",
  head() {
    return {
      title: "Joke Page",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best Place for corny jokes",
        },
      ],
    };
  },
  data() {
    return {
      jokes: [],
    };
  },
  methods:{
      async searchText(text){
        const config = {
      headers: {
        Accept: "application/json",
      },
    };

    try {
      const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config);
      this.jokes = res.data.results
    } catch (err) {
      console.log(err);
    }
      }
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json",
      },
    };

    try {
      const res = await axios.get("https://icanhazdadjoke.com/search", config);
      this.jokes = res.data.results
    } catch (err) {
      console.log(err);
    }
  },
};
</script>

<style scoped>


</style>
