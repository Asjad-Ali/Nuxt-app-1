<template>
  <div>
    <nuxt-link to="jokes">Back to jokes</nuxt-link>
    <br><br>
    
    <v-card style="padding: 1rem">
      <b>ID: </b> {{ $route.params.id }}<br><br>
     <b>Joke:</b> {{ this.joke }}
    </v-card>
      
  </div>
</template>

<script>
import axios from 'axios'
export default {
    name: "index",
    data () {
      return{
        joke: {}
      }
    },
    head () {
    return {
      title: this.joke,
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best Place for corny jokes"
        }
        

      ]
    }
    
  },

    async created() {
    const config = {
      headers: {
        Accept: "application/json",
      },
    };

    try {
      const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id }`, config);
      this.joke = res.data.joke 
    } catch (err) {
      console.log(err);
    }
  },
}
</script>

<style>

</style>