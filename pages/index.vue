<template>
<div>
  <h1 class="pa-10">
    Index Page in 
  </h1>
  <!-- <about /> -->
</div>
</template>

<script>
import about from './about.vue'
export default {
  components: { about },
  name: 'homepage',
      head () {
    return {
      title: "The HomePage",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best Place for corny jokes"
        }
        

      ]
    }
    
  }
}
</script>
